# AutoFlow Architecture Analysis

## Executive Summary

AutoFlow is a **modular monolith** architecture with clear separation between a Python FastAPI backend, Next.js frontend, and a Python core library (`autoflow-ai`). It implements a sophisticated Retrieval-Augmented Generation (RAG) system with Graph RAG capabilities, supporting multiple LLM/embedding providers with a pluggable design pattern.

---

## 1. Overall Architecture Style

### Architecture Pattern: **Modular Monolith with Clear Layering**

**Characteristics:**
- **Backend (Monolithic)**: Single FastAPI application handling all business logic
- **Frontend (SPA)**: Next.js client-side application
- **Core Library**: Standalone Python package (`autoflow-ai`) for RAG operations
- **Async Job Processing**: Celery + Redis for background tasks
- **Data Layer**: TiDB Vector database with SQLModel ORM

**Deployment Model:**
- Backend: HTTP API server (FastAPI) + Celery workers + Celery scheduler
- Frontend: Static files (Next.js build) served via reverse proxy
- Infrastructure: Docker containerization (indicated by docker-compose references)

---

## 2. Component Structure & Responsibilities

### 2.1 Backend (`/backend/app`)

#### Core Components:

| Component | Responsibility | Key Files |
|-----------|-----------------|-----------|
| **API Layer** | HTTP endpoints, request/response handling | `/api/main.py`, `/api/routes/`, `/api/admin_routes/` |
| **RAG Pipeline** | Document ingestion, indexing, retrieval, synthesis | `/rag/` (multiple submodules) |
| **Data Access Layer** | Database operations, ORM models | `/models/`, `/repositories/` |
| **Authentication** | User/API key management, session handling | `/auth/` |
| **Task Queue** | Async job processing (indexing, evaluation) | `/tasks/`, `/celery.py` |
| **Configuration** | Environment setup, runtime settings | `/core/config.py` |
| **File Storage** | Document and upload file management | `/file_storage/` |

#### API Structure:

**Public Routes** (`/api/v1/`):
- `/chats` - Chat operations (create, list, retrieve messages)
- `/chat-engines` - Chat engine configuration
- `/documents` - Document listing and retrieval
- `/retrieve` - Retrieve endpoints for RAG
- `/auth` - Authentication flows
- `/users` - User profile operations
- `/api-keys` - User API key management

**Admin Routes** (`/api/v1/admin/`):
- `/knowledge-base/` - Knowledge base CRUD
- `/knowledge-base/data-source/` - Data source management
- `/knowledge-base/document/` - Document management
- `/knowledge-base/chunk/` - Chunk operations
- `/knowledge-base/graph/` - Knowledge graph operations
- `/chat-engines/` - Chat engine admin
- `/llms/` - LLM provider configuration
- `/embedding-models/` - Embedding model configuration
- `/reranker-models/` - Reranker model configuration
- `/evaluation/` - Evaluation datasets and tasks
- `/site-settings/` - System configuration
- `/upload/` - File upload handling

### 2.2 Core Library (`/core/autoflow`)

#### Purpose
Standalone Python library providing RAG capabilities, designed for both backend integration and external use.

#### Key Modules:

| Module | Purpose |
|--------|---------|
| **KnowledgeBase** | Main abstraction for knowledge management |
| **Knowledge Graph** | Graph-based knowledge extraction and retrieval |
| **Loaders** | Document loading (PDF, Markdown, Webpage) |
| **Chunkers** | Text splitting strategies |
| **Storage** | Abstract layer for document and graph stores |
| **Models** | LLM, Embedding, and Reranker model integrations |
| **Configs** | Configuration objects for all components |

**Key Classes:**
- `Autoflow` - Factory/entry point for the library
- `KnowledgeBase` - Core abstraction for knowledge management
- `KnowledgeGraphIndex` - Knowledge graph extraction and retrieval
- `ModelManager` - Multi-provider model resolution

### 2.3 Frontend (`/frontend/app`)

#### Architecture: **Next.js with React Server Components**

**Layout Structure:**
```
src/
├── app/
│   ├── (main)/ - Main application
│   │   ├── (admin)/ - Admin panel routes
│   │   ├── (user)/ - User routes
│   │   └── c/ - Chat routes
│   ├── api/ - API proxy routes
│   └── auth/ - Authentication pages
├── api/ - API client functions (TypeScript SDK)
├── components/ - Reusable React components
├── hooks/ - Custom React hooks
└── lib/ - Utility functions
```

**Key Features:**
- Server-side rendering for initial load
- Client-side state management (Context + SWR)
- Embedded widget capability (Next.js allows exporting components)
- Multi-provider context system

---

## 3. Design Patterns Observed

### 3.1 Architectural Patterns

| Pattern | Implementation | Location |
|---------|----------------|----------|
| **Repository Pattern** | Data access abstraction | `/repositories/*.py` |
| **Service Layer** | Business logic encapsulation | `/rag/chat/chat_service.py`, `/rag/chat/chat_flow.py` |
| **Factory Pattern** | Model creation and resolution | `/core/autoflow/models/manager.py` |
| **Strategy Pattern** | Pluggable LLM/Embedding/Reranker providers | `/configs/models/providers/` |
| **Adapter Pattern** | Storage backend abstraction | `/core/autoflow/storage/doc_store/` |
| **Dependency Injection** | Database sessions, services via FastAPI `Depends()` | `/api/deps.py` |
| **Builder Pattern** | Chat flow and index configuration | `ChatFlow`, `KnowledgeBase` classes |
| **Template Method** | Base classes for extensibility | `/storage/doc_store/base.py`, `/storage/graph_store/base.py` |

### 3.2 Data Patterns

**Multi-Knowledge Base Support:**
- Knowledge bases are scoped/namespaced
- Documents belong to knowledge bases
- Chunks belong to documents
- Graph relationships scoped by namespace

**Separation of Concerns:**
- Vector search and knowledge graph are separate but complementary retrieval methods
- Multiple indexing strategies supported (VECTOR, KNOWLEDGE_GRAPH)
- Abstract DocumentStore and GraphStore interfaces

---

## 4. Code Organization

### 4.1 Backend Organization Principles

**Horizontal Layering:**
```
API Routes (endpoints)
    ↓
Service Layer (business logic: ChatFlow, ChatService)
    ↓
Repository Layer (data access)
    ↓
Models (SQLModel ORM entities)
    ↓
Database (TiDB)
```

**Vertical Slicing by Domain:**
- `/api/admin_routes/knowledge_base/` - KB admin APIs
- `/api/routes/chat.py` - Public chat APIs
- `/rag/indices/knowledge_graph/` - KG indexing
- `/rag/retrievers/knowledge_graph/` - KG retrieval
- `/rag/chat/` - Chat orchestration

### 4.2 Core Library Organization

**Module Hierarchy:**
```
autoflow/
├── main.py (entry point: Autoflow class)
├── knowledge_base/ (core abstraction)
├── knowledge_graph/ (KG extraction & retrieval)
├── storage/ (DocumentStore & GraphStore abstractions)
├── models/ (LLM, Embedding, Reranker integrations)
├── loaders/ (document loading)
├── chunkers/ (text splitting)
└── configs/ (configuration objects)
```

### 4.3 Frontend Organization

**By Feature:**
- `api/` - All API client functions (SDK)
- `components/` - Reusable UI components
- `app/(main)/` - Main application routes
- `app/(admin)/` - Admin panel routes
- `experimental/` - Feature flags and experimental features

**Separation of Concerns:**
- API clients are separate from components
- Business logic isolated in hooks
- Providers for state management (Auth, Settings, Bootstrap)

---

## 5. API Design

### 5.1 REST API Architecture

**API Format:** RESTful JSON
**Version:** `/api/v1/`
**Authentication:**
- Session-based (for web UI)
- API keys (for programmatic access)
- FastAPI Users integration

**Response Format:**
```json
{
  "status": "success|error",
  "data": {},
  "message": "optional"
}
```

**Pagination:**
- Uses `fastapi-pagination` library
- Standard `limit`/`offset` parameters
- Page-based responses with metadata

### 5.2 Request/Response Examples

**Chat Creation:**
```
POST /api/v1/chats
Content-Type: application/json

{
  "messages": [
    {"role": "user", "content": "What is this document about?"}
  ],
  "chat_engine": "default",
  "stream": true
}

Response: Server-Sent Events (SSE) stream
```

**Knowledge Base Retrieval:**
```
POST /api/v1/retrieve
{
  "query": "search query",
  "knowledge_base_id": 123,
  "top_k": 10,
  "search_mode": "vector|graph"
}
```

### 5.3 Streaming Protocol

**Chat Streaming:**
- Uses Server-Sent Events (SSE)
- Event types: `thinking`, `data`, `message`, `complete`
- Payload structure:
```python
ChatStreamDataPayload(
    type: ChatEventType,
    data: {source_nodes, answer, etc}
)
```

### 5.4 Error Handling

**Custom Exceptions Hierarchy:**
```
Exception
├── KBNotFound
├── KBDataSourceNotFound
├── ChatNotFound
└── InternalServerError
```

---

## 6. Data Flow

### 6.1 Chat Completion Flow

```
User Query (Frontend)
    ↓
POST /api/v1/chats (ChatRequest)
    ↓
ChatFlow.__init__()
├── Load ChatEngine config
├── Initialize RetrieveFlow
└── Parse chat history
    ↓
ChatFlow.chat() (generator)
├── RetrieveFlow.retrieve()
│   ├── Multiple retrieval modes (vector, graph, fusion)
│   ├── Reranking
│   └── Source document compilation
├── Response Synthesis (LLM)
└── Stream events as SSE
    ↓
Frontend receives SSE stream
└── UI updates in real-time
```

### 6.2 Document Ingestion Flow

```
User uploads document (Frontend)
    ↓
POST /api/v1/admin/documents/upload
    ↓
Store file in FileStorage
Create Document record
    ↓
Trigger build_index.py (Celery task)
├── Load document from storage
├── Parse into chunks (via node_parser)
├── Generate embeddings
├── Store in DocumentStore (TiDB Vector)
└── Extract knowledge graph (via KnowledgeGraphIndex)
│   ├── Extract entities and relationships
│   └── Store in GraphStore (TiDB)
    ↓
Update document index status
Notify frontend of completion
```

### 6.3 Knowledge Retrieval Flow

```
Query received
    ↓
RetrieveFlow.retrieve()
├── If search_mode == VECTOR:
│   └── VectorStore similarity search
├── If search_mode == KNOWLEDGE_GRAPH:
│   └── KnowledgeGraphRetriever.retrieve()
│       ├── Embed query
│       ├── Search KG nodes
│       ├── Traverse relationships (depth)
│       └── Aggregate scoring
└── Fusion (combine results)
    ↓
PostProcessing (reranking)
    ↓
Compile source documents
    ↓
Return to ChatFlow
```

### 6.4 Model Resolution Flow

```
ChatFlow initialization
    ↓
ChatEngineConfig.load_from_db()
    ↓
Resolve LLM/Embedding/Reranker
├── ModelManager.get_provider_config()
├── Merge provider config with instance config
└── Instantiate model wrapper
    ↓
Use model throughout chat session
```

---

## 7. Integration Points

### 7.1 Backend Internal Integrations

| From | To | Method | Purpose |
|------|----|---------| ---------|
| API Routes | Repository | Direct import | Data access |
| Repository | Models | ORM queries | Database operations |
| ChatFlow | RetrieveFlow | Direct instantiation | Retrieval orchestration |
| ChatFlow | LLM | Model manager | Response generation |
| Celery Tasks | Repository | Direct import | Async operations |
| Celery Tasks | KnowledgeBase (core) | Direct instantiation | Document processing |

### 7.2 Backend ↔ Core Library Integration

**Dual Use Pattern:**
1. **Backend Integration**: `/backend/app/rag/` implements RAG pipeline using `autoflow-ai`
2. **Standalone Library**: `/core/` can be used independently via `Autoflow` class

**Interface:**
```python
from autoflow import Autoflow
from autoflow.configs.db import DatabaseConfig

autoflow = Autoflow.from_config(config)
kb = autoflow.create_knowledge_base(name="my_kb")
kb.add("document.pdf")
results = kb.search("query")
```

### 7.3 Backend ↔ Frontend Integration

**Data Flow:**
1. Frontend calls TypeScript API clients
2. API clients fetch from `/api/v1/` endpoints
3. Backend returns JSON/SSE streams
4. Frontend updates React state via hooks/context

**Authentication:**
- Session cookie set on login
- Sent with every request
- API keys stored in browser for programmatic access

### 7.4 External Integrations

| Service | Purpose | Location |
|---------|---------|----------|
| OpenAI, JinaAI, LiteLLM | LLM/Embedding providers | `/configs/models/providers/` |
| TiDB | Vector database | `/core/autoflow/storage/` |
| Redis | Celery broker & caching | `/celery.py`, config |
| Langfuse | LLM observability | `/rag/chat/chat_flow.py` (optional) |
| Sentry | Error tracking | `/api_server.py` |

---

## 8. Database Schema Patterns

### 8.1 Core Tables

**Knowledge Base Hierarchy:**
```
knowledge_bases
├── id (PK)
├── name
├── namespace
└── configuration

knowledge_base_datasources (join table)
├── knowledge_base_id (FK)
└── data_source_id (FK)

documents
├── id (PK)
├── knowledge_base_id (FK)
├── source (original file)
└── metadata (JSON)

chunks (kb_chunks_{knowledge_base_id})
├── id (PK)
├── document_id (FK)
├── content
├── embedding (vector)
└── metadata (JSON)
```

**Graph Schema (in TiDB):**
```
entities
├── id
├── namespace
├── name
└── type

relationships
├── id
├── from_entity_id
├── to_entity_id
├── type
└── metadata
```

### 8.2 Special Features

**Multi-Knowledge Base Support:**
- Scoped chunk tables: `kb_chunks_{knowledge_base_id}`
- Namespace-based isolation in storage layer
- Allows fine-grained access control

**Soft Deletes:**
- `deleted_at` field on knowledge bases
- Logical deletion for data recovery

**Audit Trails:**
- `created_at`, `updated_at` timestamps
- Staff action logging for admin operations

---

## 9. Configuration Management

### 9.1 Backend Configuration

**Source:** Environment variables (`.env`)

**Key Settings:**
```python
# Database
TIDB_HOST, TIDB_PORT, TIDB_USER, TIDB_PASSWORD, TIDB_DATABASE
TIDB_SSL = True

# Task Queue
CELERY_BROKER_URL = "redis://redis:6379/0"
CELERY_RESULT_BACKEND = "redis://redis:6379/0"

# Security
SECRET_KEY (required, min 32 chars)
ENVIRONMENT = local|staging|production

# CORS
BACKEND_CORS_ORIGINS = ["http://localhost:3000"]

# Logging
LOG_LEVEL = INFO
SQLALCHEMY_LOG_LEVEL = WARNING
```

### 9.2 Core Library Configuration

**Hierarchical Config Model:**
```python
Config
├── db: DatabaseConfig
│   ├── provider: "tidb"
│   ├── host, port, user, password, database
│   └── ssl_verify

Models Configuration:
├── LLMConfig(provider, config)
├── EmbeddingModelConfig(provider, config)
└── RerankerConfig(provider, config)
```

**Provider Config Merger:**
1. Load provider defaults
2. Merge with instance config
3. Create model instance

---

## 10. Asynchronous Processing

### 10.1 Celery Task Architecture

**Task Queue Routing:**
```python
app.conf.task_routes = [
    {"app.tasks.evaluate.*": {"queue": "evaluation"}},
    {"*": {"queue": "default"}},
]
```

**Tasks Defined:**
| Task | Queue | Purpose |
|------|-------|---------|
| `build_index` | default | Index documents after upload |
| `knowledge_base.*` | default | KB operations |
| `evaluate.*` | evaluation | Evaluation tasks |

### 10.2 Task Implementation Pattern

```python
@shared_task
def build_index_task(doc_id: UUID, kb_id: int):
    # Load document
    # Parse into chunks
    # Generate embeddings
    # Store in database
    # Extract KG
    # Update status
```

---

## 11. Security Architecture

### 11.1 Authentication

**Mechanisms:**
- Session-based (web UI): Secure HTTP-only cookies
- API Key-based (programmatic): Token in header

**Implementation:**
```python
# FastAPI Users integration
fastapi_users.get_auth_router(auth_backend)

# API Key custom implementation
class APIKeyAuth(HTTPBearer)
```

### 11.2 Authorization

**Fine-grained Access Control:**
- User can only view/edit own chats
- API keys scoped to user
- Admin routes protected with role checks

**Patterns:**
```python
user = await CurrentUserDep()  # Dependency injection
if not user_can_view_chat(user, chat):
    raise PermissionError()
```

### 11.3 Data Protection

**In Transit:**
- TLS/SSL for database connections
- HTTPS enforced in production

**At Rest:**
- API keys hashed in database
- Secrets managed via environment

---

## 12. Performance Considerations

### 12.1 Caching Strategies

**Query Caching:**
- Question cache (optional): `ENABLE_QUESTION_CACHE`
- Semantic cache in `/rag/semantic_cache/`

**Database Connection Pooling:**
```python
pool_size=20, max_overflow=40, pool_recycle=300
pool_pre_ping=True  # Health checks
```

### 12.2 Async/Parallel Processing

**Backend:**
- Async routes with `async def`
- Celery for background jobs
- ThreadPoolExecutor in knowledge base operations

**Frontend:**
- SWR for data fetching with caching
- React Server Components for initial render
- Progressive enhancement

### 12.3 Vector Database Optimization

**TiDB Vector:**
- Vector similarity search using native functions
- Efficient nearest neighbor queries
- Scalable to large documents

---

## 13. Testing Architecture

### 13.1 Core Library Tests

**Test Types:**
- Unit tests: Model managers, storage implementations
- Integration tests: Knowledge base operations
- Tests for TiDB doc store and graph store

**Test Framework:** pytest

### 13.2 E2E Tests

**Framework:** Playwright (JavaScript)

**Test Coverage:**
- Widget functionality
- Chat flow
- Knowledge base management
- Data source operations
- API key management
- Settings configuration

---

## 14. Deployment Architecture

### 14.1 Docker Compose Structure

**Services:**
1. **FastAPI Backend** - Main application server
2. **Celery Worker** - Task execution
3. **Celery Beat** - Scheduled tasks
4. **Redis** - Broker and cache
5. **TiDB** - Vector database

### 14.2 Environment Separation

**Environments:**
- `local` - Development
- `staging` - Pre-production
- `production` - Production

**Configuration by Environment:**
- SSL verification
- CORS origins
- Logging levels
- Sentry integration

---

## 15. Key Architectural Decisions

### 15.1 Why Modular Monolith?

**Advantages:**
- Clear separation of concerns (backend, frontend, core library)
- Core library can be used independently
- Monolithic backend simplifies deployment initially
- Easy to split services later if needed

### 15.2 Dual Indexing Strategy (Vector + Knowledge Graph)

**Rationale:**
- Vector search: Fast semantic similarity
- Knowledge graph: Structured reasoning and relationships
- Complementary retrieval methods
- Users can choose search mode

### 15.3 Multi-Provider Support

**Design:**
- Strategy pattern for pluggable providers
- Configuration-driven model resolution
- Factory pattern for instantiation
- Supports: OpenAI, JinaAI, LiteLLM, custom

### 15.4 Repository Pattern for Data Access

**Benefits:**
- Abstraction over SQLModel/SQLAlchemy
- Easier testing via mocking
- Consistent query patterns
- Single source of truth for data operations

### 15.5 Streaming Responses

**Why SSE?**
- Server can send events as they happen
- No need for websockets
- Works with standard HTTP
- Natural fit for streaming LLM outputs

---

## 16. Technology Stack Summary

### Backend
| Layer | Technology |
|-------|-----------|
| Framework | FastAPI |
| ORM | SQLModel |
| Database | TiDB Vector |
| Task Queue | Celery |
| Message Broker | Redis |
| RAG | LlamaIndex, DSPy |
| LLMs | LiteLLM (multi-provider) |
| Auth | FastAPI Users |
| Observability | Sentry, Langfuse |

### Frontend
| Layer | Technology |
|-------|-----------|
| Framework | Next.js 13+ |
| Language | TypeScript |
| Styling | CSS Modules / Tailwind |
| State Mgmt | React Context, SWR |
| Testing | Playwright (E2E) |

### Core Library
| Component | Technology |
|-----------|-----------|
| RAG Pipeline | LlamaIndex |
| Program Synthesis | DSPy |
| Storage Abstraction | Custom interfaces |
| Embedding Models | Various providers |
| LLM Integration | LiteLLM |

---

## 17. Extensibility Points

### 17.1 Adding New Storage Backend

```python
# Extend base class
class CustomDocumentStore(DocumentStore):
    def add(self, documents: List[Document]) -> List[Document]:
        # Custom implementation

    def search(self, query: str, top_k: int) -> DocumentSearchResult:
        # Custom implementation
```

### 17.2 Adding New LLM Provider

```python
# Add provider config
class CustomProviderConfig(ProviderConfig):
    api_key: str
    model: str

# Register with ModelManager
model_manager.registry_provider(
    ModelProviders.CUSTOM,
    CustomProviderConfig()
)
```

### 17.3 Custom Chat Engine

```python
# Extend ChatEngineConfig
class CustomChatEngine(ChatEngineConfig):
    def get_chat_engine(self):
        # Return custom retriever + synthesizer combo
```

---

## 18. Known Limitations & Constraints

1. **Single Monolithic Backend** - May need splitting at scale
2. **TiDB-specific** - Core library tied to TiDB vector storage
3. **Synchronous Session Management** - Scoped sessions for multi-threading
4. **Knowledge Base Namespace** - Currently string-based, not RBAC
5. **No GraphQL** - REST-only API (decision to keep simple)

---

## 19. Future Architecture Considerations

1. **Microservices Migration Path**
   - Extract RAG pipeline into separate service
   - Dedicated chat service
   - Separate knowledge management service

2. **Multi-Backend Support**
   - Abstract TiDB-specific code
   - Support Postgres, MongoDB
   - Plugin architecture for storage

3. **Advanced Evaluation Framework**
   - RAGAS integration
   - Automated metric tracking
   - Performance benchmarking

4. **Enhanced Caching Layer**
   - Semantic caching improvements
   - Multi-level caching (memory, Redis)
   - Cache invalidation strategies

---

## Conclusion

AutoFlow demonstrates a well-architected **modular monolith** with:
- Clear layering and separation of concerns
- Pluggable design patterns throughout
- Sophisticated RAG capabilities with dual indexing
- Production-ready infrastructure (async processing, observability)
- Extensibility at multiple levels (storage, models, chat engines)

The architecture enables both:
- **Standalone use** via the core library
- **Integrated use** as a complete platform

This makes AutoFlow suitable for both enterprise adoption and developer communities seeking RAG solutions.
