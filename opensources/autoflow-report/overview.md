# AutoFlow - Overview

## Executive Summary

AutoFlow is an open-source Graph RAG (Retrieval-Augmented Generation) based conversational knowledge base tool built on TiDB Serverless Vector Storage, LlamaIndex, and DSPy. Developed by PingCAP, it transforms static documentation sites into intelligent, Perplexity-style conversational search interfaces where users can ask natural language questions and receive context-aware answers backed by knowledge graph understanding. The platform features an embeddable JavaScript widget for seamless website integration, making it ideal for product documentation chatbots and customer support applications.

With 2.7k GitHub stars and active development (v0.4.0 released January 2025), AutoFlow is in early-stage development with plans to become a pip-installable Python package. The project combines cutting-edge AI technologies with practical deployment patterns, offering a modular architecture that separates FastAPI backend services, Next.js frontend, and a standalone autoflow-ai core library. Its unique dual-index RAG approach (vector search + knowledge graph) enables multi-hop relationship queries that go beyond simple semantic search.

AutoFlow is best suited for organizations with extensive documentation that want to provide conversational AI-powered search without heavy enterprise infrastructure. However, its early-stage maturity, synchronous architecture limiting concurrent request handling, and steep setup requirements (TiDB, Redis, multiple microservices) require careful evaluation before production deployment.

## Technology Stack

- **Primary Languages**: Python 3.10+ (50%, backend/AI), TypeScript 5.7 (40%, frontend)
- **Key Technologies**: TiDB Vector, LlamaIndex, DSPy, LiteLLM, Next.js 15, React 19, FastAPI
- **Frontend Framework**: Next.js 15 with React 19, Tailwind CSS, shadcn/ui, Radix UI
- **Backend Framework**: FastAPI with SQLModel ORM, Celery + Redis for async tasks
- **AI/ML Stack**: LlamaIndex (RAG), DSPy (prompt engineering), 7+ LLM providers (OpenAI, Azure, Gemini, Bedrock, Ollama), multiple embedding/reranking options
- **Database & Storage**: TiDB Vector (distributed SQL + vector), Redis (caching)
- **Build Tools**: pnpm 9.15 (frontend), Docker Compose (deployment)
- **Testing**: Jest, Playwright (E2E), pytest

## Primary Use Cases

1. **Product Documentation Chatbots**: Companies with extensive API or product documentation deploy AutoFlow to provide instant conversational support on their docs sites. Users ask natural language questions instead of navigating nested documentation menus. The embeddable widget integrates seamlessly into existing websites (example: https://tidb.ai).

2. **In-Product Customer Support Widget**: SaaS and service companies embed the JavaScript widget to field common product questions 24/7, handling FAQs, pricing questions, feature explanations, and troubleshooting automatically to reduce support ticket volume.

3. **Knowledge Base Construction for Enterprise**: Organizations build internal knowledge bases from technical documentation, wikis, and policy documents. AutoFlow's graph RAG approach enables search across multiple documents and relationships, improving institutional knowledge accessibility and reducing time to find information.

## Key Pros & Cons

**Pros:**
- **Graph RAG Architecture**: Dual-index approach combining vector search with knowledge graphs enables multi-hop relationship queries and richer semantic understanding beyond simple vector similarity
- **Multi-Provider Flexibility**: Supports 7+ LLM providers (OpenAI, Azure, Gemini, Bedrock, Ollama), multiple embedding models, and 4 reranking options with local self-hosted alternatives for data privacy
- **Embeddable Widget**: Simple JavaScript snippet integration enables instant deployment on existing websites without backend changes, making it easy to add conversational search to documentation sites
- **TiDB Integration**: Native SQL + vector storage in single database eliminates separate vector DB infrastructure, simplifying operational complexity and enabling hybrid SQL/vector queries
- **Production Demo**: Live deployment at tidb.ai demonstrates real-world viability, and Docker Compose setup with minimal resource requirements (4 CPU cores, 8GB RAM) enables quick starts

**Cons:**
- **No Async/Await**: Zero async implementations in chat and retrieval modules limits concurrent request handling; single instance likely handles only 50-100 concurrent users before performance degradation
- **Minimal Test Coverage**: Only 16 test files across 331 Python files with no tests for core RAG modules; multiple FIXME comments in critical paths indicate incomplete production readiness
- **Knowledge Graph Extraction Overhead**: DSPy-based extraction requires separate LLM calls per chunk (2-3x latency), significantly slowing indexing; 10 documents can take 2-5 minutes depending on LLM provider
- **Steep Setup Requirements**: Requires provisioning TiDB (Cloud or self-managed), Redis, multiple microservices, and understanding of 5-layer architecture (datasource → parser → embedder → indexer → retriever)
- **Early-Stage Maturity**: v0.4.0 with limited documentation (2,705 lines, no architectural diagrams), no multi-tenancy, and production features like semantic cache still in beta; lower market traction (2.7k stars) compared to alternatives

## Main Alternatives

- **RAGFlow (70.3k stars)**: Enterprise-grade RAG engine with 40+ data connectors, agentic capabilities, and more mature ecosystem. Choose for large-scale enterprise data pipelines and diverse document processing needs. Backed by InfiniFlow with significant community adoption.

- **Quivr (37k-38.7k stars)**: Flexible RAG framework with multi-LLM support and second-brain philosophy. Choose for building custom RAG applications with maximum flexibility, personal knowledge management, or when easier integration into existing products is needed. Less opinionated than AutoFlow.

- **Onyx/Danswer (12.1k stars, $10M funding)**: Enterprise search platform with 40+ native connectors (Google Drive, Confluence, Slack), RBAC, and multi-tenancy. Choose for large organizations needing unified search across multiple data sources with strong access control and commercial support.

---

*Analysis generated: 2025-12-27*
*Source: https://github.com/pingcap/autoflow*
