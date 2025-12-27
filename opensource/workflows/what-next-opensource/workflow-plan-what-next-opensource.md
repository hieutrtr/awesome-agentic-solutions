---
stepsCompleted: [1, 2, 3, 4, 5, 6, 7]
workflowCreationComplete: true
buildDate: 2025-12-24
---

# Workflow Creation Plan: what-next-opensource

## Initial Project Context

- **Module:** standalone
- **Target Location:** /home/hieutt50/projects/ALLMAD-METHOD/_bmad-output/bmb-creations/workflows/what-next-opensource/
- **Created:** 2025-12-24

## Workflow Vision

A strategic open source planning workflow that helps developers identify high-potential open source project opportunities through interactive brainstorming and trend analysis.

### Purpose
- Interactive brainstorming sessions to discover trending opportunities
- Domain/topic-specific analysis
- Strategic positioning for GitHub star growth
- Data-driven opportunity identification

### Target Users
- Developers looking to create impactful open source projects
- Tech entrepreneurs exploring open source opportunities
- Contributors seeking high-value projects to build

---

## Comprehensive Requirements

### 1. Workflow Purpose and Scope

**Primary Goal:** Help developers identify open source project ideas that make people's work better and easier.

**Process:**
- User provides a topic/domain
- AI researches websites and communities
- Collaborative discussion to refine and identify appropriate projects
- Generate technical specification for validated idea

**Success Definition:** Good idea confirmed by user and ready for development.

### 2. Workflow Type Classification

**Type:** Hybrid Workflow
- **Interactive Component:** Brainstorming and collaborative discussion
- **Document Generation:** Produces technical specification document
- **Research-Driven:** Web search and community insights integration

### 3. Workflow Flow and Step Structure

**Pattern:** Iterative Brainstorming with Trend Analysis

**Proposed Step Sequence:**
1. Define domain/topic of interest (user input)
2. Analyze current trends (web search, GitHub trends, community discussions)
3. Generate multiple project ideas (iterative/loop - can repeat)
4. Compare and rank opportunities
5. Deep-dive into selected option(s)
6. Generate technical specification document

**Flow Characteristics:**
- Iterative ideation phase (Step 3 can loop)
- Decision points for user selection
- Progressive refinement from broad to specific

### 4. User Interaction Style

**Interaction Pattern:** Question-based with Options

**Key Characteristics:**
- AI asks clarifying questions at decision points
- Present options (A, B, C) for user to select
- Collaborative discussion to refine ideas
- User drives direction through selections
- Conversational but structured

**Balance:**
- Highly collaborative during ideation
- Guided during decision points
- User confirms final direction

### 5. Instruction Style

**Hybrid Approach:**

**Intent-Based (for research/analysis):**
- Research phase: AI adapts conversation naturally
- Trend analysis: Flexible exploration
- Example: "Let me analyze top GitHub trends in [domain]..."

**Prescriptive (for decision points):**
- Clear options at selection moments
- Structured choices for user
- Example: "Which direction interests you? A) Developer tools B) Data visualization C) AI integration"

### 6. Input Requirements

**Required Inputs:**
- Topic/domain from user (e.g., "developer productivity", "data science", "web3")

**Optional Inputs (to enhance results):**
- User's technical expertise/preferences
- Time commitment available for development
- Target audience for the project
- Existing projects the user admires or wants to build upon

**Prerequisites:**
- Internet access for web research
- Access to GitHub trends and community data

### 7. Output Specifications

**Primary Output:** Technical Specification Document

**Document Contents:**
- Project overview and value proposition
- Target users and use cases
- Core features and functionality
- Technical architecture/stack recommendations
- Implementation roadmap
- Competitive analysis
- Success metrics (star potential, adoption indicators)

**Format:**
- Markdown document
- Saved to `_bmad-output/` folder
- Structured and ready for implementation

**Intermediate Outputs:**
- Trend analysis summary
- Project idea candidates list
- Comparison matrix of opportunities

### 8. Success Criteria

**Primary Success Indicator:**
- Good idea confirmed by user ✅

**Supporting Success Metrics:**
- Clear differentiation from existing solutions
- Validated demand through trend data and community signals
- Feasible scope for user to implement
- High star potential based on similar projects
- Addresses real pain points for target users
- User feels confident to proceed with development

---

## Tools Configuration

### Core BMAD Tools

- **Party-Mode**: ✅ Included
  - **Integration points**: Step 3 (Generate multiple project ideas)
  - **Purpose**: Multi-persona brainstorming for creative ideation with diverse AI perspectives on open source opportunities

- **Advanced Elicitation**: ✅ Included
  - **Integration points**: Step 5 (Deep-dive into selected options)
  - **Purpose**: Critical questioning and validation to ensure thorough evaluation before committing to development

- **Brainstorming**: ✅ Included
  - **Integration points**: Step 1 (Define domain) and Step 3 (Idea generation)
  - **Purpose**: Structured creative exploration for domain discovery and iterative ideation

### LLM Features

- **Web-Browsing**: ✅ Included - **ESSENTIAL**
  - **Use cases**: GitHub trends analysis, community research (Stack Overflow, Reddit, HackerNews), real-time data collection
  - **Why critical**: Core requirement for analyzing current trends and validating demand

- **File I/O**: ✅ Included - **REQUIRED**
  - **Operations**: Create and update technical specification document, save intermediate research results
  - **Why critical**: Primary output is a markdown document that must be generated and managed

- **Sub-Agents**: ❌ Excluded
  - **Reason**: Workflow complexity doesn't justify overhead; sequential research is sufficient

- **Sub-Processes**: ❌ Excluded
  - **Reason**: Not needed for this workflow pattern

### Memory Systems

- **Sidecar File**: ✅ Included
  - **Purpose**: Track explored domains, dismissed ideas, lessons learned from previous sessions
  - **Benefits**: Avoid repeating research, learn from past explorations, enable session continuity
  - **Use cases**: Remember what topics were already explored, track why certain ideas were rejected, pick up where user left off

### External Integrations

- **Context-7**: ✅ Included
  - **Purpose**: Access curated API documentation and technical references
  - **Use cases**:
    - Reading library/framework documentation when evaluating tech stacks
    - Finding limitations and gotchas of existing tools
    - Making informed architecture decisions in technical specification
  - **Integration points**: Step 5 (Deep-dive) and Step 6 (Generate technical spec)
  - **⚠️ Requires installation**: Yes

### Installation Requirements

**Tools Requiring Installation:**
- Context-7 MCP Server
  - **Installation effort**: ~5-10 minutes one-time setup
  - **Process**: Standard MCP server installation
  - **Documentation**: https://github.com/modelcontextprotocol/servers/tree/main/src/context-7

**User Installation Preference:** Willing to install

**Workflow Behavior:**
- Installation instructions will be provided in workflow documentation
- Context-7 enhances workflow quality by providing accurate technical references
- Workflow will guide user through setup if not already installed

---

## Output Format Design

**Format Type**: Structured

**Output Requirements**:
- Document type: Technical Specification Document
- File format: Markdown (.md)
- Frequency: Single document per workflow execution
- Saved to: `_bmad-output/` folder

**Structure Specifications**:

**Required Sections:**
1. **Project Overview and Value Proposition**
   - Problem statement
   - Solution description
   - Key value propositions
   - Differentiation from existing solutions

2. **Target Users and Use Cases**
   - Primary user personas
   - User scenarios
   - Key use cases
   - User pain points addressed

3. **Core Features and Functionality**
   - Feature list with descriptions
   - Feature prioritization (MVP vs future)
   - Functionality specifications

4. **Technical Architecture and Stack Recommendations**
   - Recommended technology stack
   - Architecture decisions and rationale
   - System design overview
   - Integration points

5. **Implementation Roadmap**
   - Development phases
   - Milestone definitions
   - Timeline considerations
   - Resource requirements

6. **Competitive Analysis**
   - Existing solutions comparison
   - Market positioning
   - Competitive advantages
   - Gap analysis

7. **Success Metrics**
   - GitHub star potential indicators
   - Adoption metrics
   - Community engagement measures
   - Quality indicators

**Intermediate Outputs:**
- Trend analysis summary (markdown snippet)
- Project idea candidates list (markdown table)
- Comparison matrix (markdown table)

**Template Information**:
- Template source: AI-generated structured format
- Template approach: Progressive document building through workflow steps
- Frontmatter tracking: `stepsCompleted` array to track workflow progress

**Special Considerations**:
- Document should be immediately actionable for development
- Technical recommendations must be current and well-justified
- Competitive analysis must be data-driven from research
- Success metrics should be measurable and realistic

---

## Workflow Structure Design

### Continuation Support Assessment

**Decision:** YES - Continuation support is REQUIRED

**Rationale:**
- Workflow generates a comprehensive technical specification document
- Users will likely need to pause and resume (research is time-intensive)
- Extensive data collection and analysis across multiple sources
- Complex decisions require careful consideration across sessions

**Implementation:**
- Include step-01-init.md with continuation detection logic
- Include step-01b-continue.md for seamless workflow resumption
- Every step updates `stepsCompleted` array in output document frontmatter
- Sidecar file tracks explored domains and dismissed ideas across sessions

### Step Structure (7 Steps Total)

#### **Step 01: Initialization** (`step-01-init.md`)
- **Goal:** Initialize workflow, detect continuation, create output document
- **Type:** Auto-proceed (no menu)
- **Key Actions:**
  - Check for existing output document
  - Route to step-01b-continue.md if workflow in progress
  - Create new output document from template with frontmatter
  - Welcome user to the process
- **Next:** Auto-proceed to step 02

#### **Step 01b: Continuation** (`step-01b-continue.md`)
- **Goal:** Resume workflow from previous session
- **Type:** Confirmation menu ([C] Continue)
- **Key Actions:**
  - Analyze `stepsCompleted` from frontmatter
  - Read all completed step files for context
  - Welcome user back with progress summary
  - Determine appropriate next step
- **Next:** Load appropriate next step based on progress

#### **Step 02: Domain Definition** (`step-02-domain-definition.md`)
- **Goal:** Define topic/domain of interest with collaborative exploration
- **Type:** Standard menu ([A] Advanced Elicitation [B] Brainstorming [P] Party Mode [C] Continue)
- **Key Actions:**
  - Gather domain/topic from user through conversation
  - Optional: Collect technical expertise, target audience, time commitment
  - Optional: Brainstorming task for domain exploration
  - Document domain scope and user preferences
  - Update output document with domain section
- **Tools:** Brainstorming task integration
- **Next:** Step 03

#### **Step 03: Trend Analysis** (`step-03-trend-analysis.md`)
- **Goal:** Analyze current trends using web research and GitHub data
- **Type:** Standard menu ([A] Advanced Elicitation [P] Party Mode [C] Continue)
- **Key Actions:**
  - Web search for domain trends (GitHub Trending, HackerNews, Reddit, Stack Overflow)
  - Analyze GitHub repositories in the domain (stars, forks, activity)
  - Identify community discussions and pain points
  - Compile trend analysis summary
  - Update output document with trends section
- **Tools:** Web-browsing (ESSENTIAL)
- **Next:** Step 04

#### **Step 04: Ideation** (`step-04-ideation.md`)
- **Goal:** Generate multiple project ideas iteratively
- **Type:** Iterative menu ([A] Advanced Elicitation [P] Party Mode [G] Generate More Ideas [C] Continue)
- **Key Actions:**
  - Generate 3-5 project ideas based on trends and domain
  - Optional: Party-Mode for multi-persona brainstorming
  - User can request more ideas (loops back to ideation)
  - Document all project idea candidates in table format
  - Update output document with candidates section
- **Tools:** Party-Mode integration for creative ideation
- **Special:** Allows looping back to generate more ideas before continuing
- **Next:** Step 05 (or loop back if user selects [G])

#### **Step 05: Ranking** (`step-05-ranking.md`)
- **Goal:** Compare and rank project opportunities
- **Type:** Standard menu ([A] Advanced Elicitation [P] Party Mode [C] Continue)
- **Key Actions:**
  - Present comparison matrix framework (Star Potential, Feasibility, Differentiation, Market Demand)
  - Evaluate each project idea against criteria
  - Rank opportunities with justification
  - User selects top 1-2 ideas for deep-dive
  - Update output document with comparison matrix and ranking
- **Next:** Step 06

#### **Step 06: Deep-Dive** (`step-06-deep-dive.md`)
- **Goal:** Deep-dive analysis of selected project idea(s)
- **Type:** Standard menu ([A] Advanced Elicitation [P] Party Mode [C] Continue)
- **Key Actions:**
  - Detailed competitive analysis (existing solutions, gaps)
  - Market positioning exploration
  - Feature set definition with prioritization
  - Architecture considerations using Context-7 for library/framework research
  - Advanced Elicitation for critical validation
  - Update output document with deep-dive analysis
- **Tools:** Context-7 for technical documentation, Advanced Elicitation for validation
- **Next:** Step 07

#### **Step 07: Technical Specification** (`step-07-tech-spec.md`)
- **Goal:** Generate comprehensive technical specification document
- **Type:** Final menu ([A] Advanced Elicitation [C] Complete Workflow)
- **Key Actions:**
  - Synthesize all research into final technical spec
  - Complete all required sections (Project Overview, Features, Architecture, Roadmap, Success Metrics)
  - Use Context-7 for accurate tech stack recommendations
  - Mark workflow as complete in frontmatter
  - Present final document to user
  - Update `stepsCompleted` with step 7 and mark `workflowComplete: true`
- **Tools:** Context-7 for technical accuracy
- **Next:** None (workflow complete)

### Interaction Pattern Design

**User Input Points:**
- Step 02: Domain/topic definition, optional preferences
- Step 04: Review ideas, request more ideas, select candidates
- Step 05: Evaluate criteria, select top ideas for deep-dive
- Step 06: Validate analysis, confirm direction
- Step 07: Final review and approval

**Autonomous Work Phases:**
- Step 03: Web research and trend analysis
- Step 04: Idea generation (with user review)
- Step 05: Ranking and comparison matrix
- Step 06: Deep-dive research and competitive analysis
- Step 07: Technical specification synthesis

**Confirmation Points:**
- End of each step via [C] Continue menu option
- Step 04: Explicit choice to generate more ideas or proceed
- Step 05: Selection of ideas for deep-dive
- Step 07: Final workflow completion

### Data Flow Design

**Input Data:**
- User-provided domain/topic (Step 02)
- Optional user preferences (technical expertise, target audience, time commitment)
- Web research data (Step 03)
- User selections and preferences throughout

**Step-by-Step Data Flow:**
1. **Step 02 → Output:** Domain definition, user preferences
2. **Step 03 → Output:** Trend analysis summary, GitHub trends, community insights
3. **Step 04 → Output:** Project idea candidates list (markdown table)
4. **Step 05 → Output:** Comparison matrix, ranked opportunities
5. **Step 06 → Output:** Deep-dive analysis, competitive analysis, feature definitions
6. **Step 07 → Output:** Complete technical specification document

**State Tracking:**
- `stepsCompleted` array in frontmatter tracks progress
- `lastStep` field indicates last completed step name
- `workflowComplete` boolean marks final completion
- `inputDocuments` array (empty for this workflow, no input docs needed)
- `exploredDomains` array in sidecar file tracks historical searches

**Error Handling:**
- If web-browsing fails: Notify user, provide fallback manual input option
- If Context-7 unavailable: Workflow continues without it, notes limitation
- If user provides invalid domain: Ask clarifying questions
- If no ideas generated: Loop back to domain refinement

### File Structure Design

**Workflow Root:** `{targetWorkflowPath}/`

**Core Files:**
- `workflow.md` - Main workflow configuration and architecture
- `README.md` - Installation and usage instructions

**Steps Folder:** `steps/`
- `step-01-init.md`
- `step-01b-continue.md`
- `step-02-domain-definition.md`
- `step-03-trend-analysis.md`
- `step-04-ideation.md`
- `step-05-ranking.md`
- `step-06-deep-dive.md`
- `step-07-tech-spec.md`

**Templates Folder:** `templates/`
- `output-template.md` - Initial structure for technical spec document with frontmatter

**Data Folder:** (Not needed for this workflow)
- No static data files required

**Supporting Files:**
- Sidecar file managed by BMAD memory system (automatic)

### Role and Persona Definition

**AI Role:** Strategic Open Source Advisor & Trend Analyst

**Expertise:**
- Open source ecosystem and GitHub trends analysis
- Technology landscape and emerging patterns
- Competitive analysis and market positioning
- Technical architecture and stack recommendations
- Community engagement and adoption strategies

**Communication Style:**
- Collaborative and exploratory during research phases
- Data-driven and analytical when presenting findings
- Encouraging and creative during ideation
- Critical and thorough during validation (Advanced Elicitation)
- Structured and professional in final deliverable

**Tone:**
- Question-based with clear options at decision points
- Intent-based for research and analysis (adaptive conversation)
- Prescriptive for decision points (A/B/C choices)
- Supportive and constructive throughout

**User Partnership:**
- AI brings: Research capabilities, trend analysis, technical knowledge
- User brings: Domain expertise, project goals, preferences, final decisions
- Together create: Data-driven, validated open source project plan

### Validation and Quality Assurance

**Step-Level Validation:**
- Step 02: Ensure domain is clearly defined and scoped
- Step 03: Validate trends with multiple data sources
- Step 04: Minimum 3 project ideas before proceeding
- Step 05: User explicitly selects ideas for deep-dive
- Step 06: Advanced Elicitation validates analysis depth
- Step 07: All required sections complete in technical spec

**Output Quality Checks:**
- Technical spec includes all 7 required sections
- Competitive analysis based on real research data
- Architecture recommendations reference actual libraries/frameworks (via Context-7)
- Success metrics are measurable and realistic
- Implementation roadmap is actionable

**Error Recovery:**
- Each step allows return to previous step if needed (through user conversation)
- Can restart ideation at Step 04 if ideas aren't satisfactory
- Can refine domain at Step 02 via conversation before continuing

**Success Criteria:**
- User explicitly confirms satisfaction with final technical spec
- All required sections populated with quality content
- Research-backed recommendations
- `workflowComplete: true` in frontmatter

### Special Features

**Iterative Ideation Loop (Step 04):**
- Menu option [G] "Generate More Ideas" allows looping back
- Accumulates all ideas in a single table
- Prevents premature convergence on first batch of ideas
- User controls when to proceed to ranking

**Multi-Source Research (Step 03):**
- GitHub Trending for star patterns
- HackerNews for community discussion
- Reddit for pain points and user needs
- Stack Overflow for technical challenges
- Synthesizes insights across sources

**Context-7 Integration (Steps 06-07):**
- Queries library/framework documentation for accuracy
- Identifies limitations and gotchas
- Informs architecture decisions with current information
- Falls back gracefully if unavailable

**Sidecar Memory (Cross-Session):**
- Tracks previously explored domains
- Records dismissed project ideas with reasons
- Learns from past workflow executions
- Prevents redundant research

**Party-Mode Integration (Steps 02, 04):**
- Step 02: Multi-persona domain exploration
- Step 04: Creative ideation from diverse AI perspectives
- User-invoked when seeking additional creative input

**Advanced Elicitation Integration (Steps 05, 06, 07):**
- Step 05: Critical evaluation of ranking criteria
- Step 06: Deep validation of project viability
- Step 07: Final technical spec quality review

### Design Review Summary

**Workflow Progression:**
Init → Domain → Trends → Ideas → Ranking → Deep-Dive → Tech Spec

**Total Steps:** 7 (plus 1b continuation step)

**Estimated Duration:** 2-4 sessions (research-intensive)

**User Engagement:** High collaboration with autonomous research phases

**Tools Integration:** All configured tools properly placed

**Output Quality:** Comprehensive, actionable technical specification

**Flexibility:** Supports pause/resume, iterative ideation, multi-session work

**Success Criteria:** User-confirmed, validated, research-backed project plan

---

## Build Summary

**Build Date:** 2025-12-24
**Build Status:** ✅ Complete

### Files Created

**Workflow Root:** `/home/hieutt50/projects/ALLMAD-METHOD/_bmad-output/bmb-creations/workflows/what-next-opensource/`

#### Core Configuration Files
- ✅ `workflow.md` (3.2 KB)
  - Main workflow configuration with step-file architecture
  - Role definition: Strategic Open Source Advisor & Trend Analyst
  - Initialization sequence pointing to step-01-init.md

- ✅ `README.md` (6.6 KB)
  - Complete user documentation
  - Installation instructions with Context-7 setup guidance
  - Usage guide for all 7 workflow steps
  - Troubleshooting section
  - Tips for best results

#### Template Files
- ✅ `templates/output-template.md` (1.1 KB)
  - Initial structure for technical spec document
  - Frontmatter fields: stepsCompleted, lastStep, workflowComplete, date, user_name, domain, exploredDomains, projectIdeas, selectedIdea
  - Placeholder sections for all 7 specification sections

#### Step Files (8 total)

**Initialization Steps:**
- ✅ `steps/step-01-init.md` (6.7 KB)
  - Continuation detection logic
  - Routes to step-01b-continue.md if workflow in progress
  - Creates initial document from template with frontmatter
  - Auto-proceeds to step 02

- ✅ `steps/step-01b-continue.md` (7.3 KB)
  - Handles workflow resumption from previous session
  - Analyzes stepsCompleted array to determine last completed step
  - Reads all completed step files for context
  - Welcome back dialog with progress summary

**Main Workflow Steps:**
- ✅ `steps/step-02-domain-definition.md` (8.8 KB)
  - Collaborative domain/topic exploration
  - Optional Brainstorming tool integration
  - Documents domain definition in output file
  - Menu: [A] Advanced Elicitation [B] Brainstorming [P] Party Mode [C] Continue

- ✅ `steps/step-03-trend-analysis.md` (10.3 KB)
  - Multi-source web research (GitHub, HackerNews, Reddit, Stack Overflow, Tech Blogs)
  - Documents popular projects, pain points, technical challenges, market opportunities
  - User validation of findings before documentation
  - Menu: [A] Advanced Elicitation [P] Party Mode [C] Continue

- ✅ `steps/step-04-ideation.md` (10.3 KB)
  - Generates 3-5 project ideas per iteration
  - **Special iterative feature**: [G] Generate More Ideas loops back for additional batches
  - Accumulates all ideas across iterations
  - Menu: [A] Advanced Elicitation [P] Party Mode [G] Generate More Ideas [C] Continue

- ✅ `steps/step-05-ranking.md` (11.1 KB)
  - Systematic evaluation using 4 criteria: Star Potential, Feasibility, Differentiation, Market Demand
  - Creates comparison matrix with scores and justifications
  - User selects 1-2 ideas for deep-dive
  - Menu: [A] Advanced Elicitation [P] Party Mode [C] Continue

- ✅ `steps/step-06-deep-dive.md` (14.2 KB)
  - Comprehensive competitive analysis with web research
  - Complete feature planning (MVP/V2/Future prioritization)
  - Architecture exploration with Context-7 integration
  - Critical validation phase
  - Menu: [A] Advanced Elicitation [P] Party Mode [C] Continue

- ✅ `steps/step-07-tech-spec.md` (18.3 KB)
  - Final synthesis of all research into comprehensive technical specification
  - 7 required sections: Project Overview, Target Users, Core Features, Technical Architecture, Implementation Roadmap, Competitive Analysis, Success Metrics
  - Marks workflowComplete: true in frontmatter
  - Menu: [A] Advanced Elicitation [C] Complete Workflow (FINAL STEP)

### Architecture Implementation

**Pattern:** Step-file architecture with continuation support
- Micro-file design: Each step is self-contained instruction file
- Just-in-time loading: Only current step file loaded at a time
- Sequential enforcement: Steps must be completed in order
- State tracking: Progress tracked via stepsCompleted array in frontmatter
- Append-only building: Document built progressively across steps

**Special Features Implemented:**
1. **Continuation Support** (Steps 01 and 01b)
   - Detects existing output document
   - Routes to continuation step when workflow in progress
   - Preserves full context across sessions

2. **Iterative Ideation** (Step 04)
   - [G] menu option allows looping back for more ideas
   - Accumulates all ideas in single table
   - Prevents premature convergence

3. **Multi-Source Research** (Step 03)
   - GitHub Trending analysis
   - HackerNews community discussions
   - Reddit pain points
   - Stack Overflow technical challenges
   - Tech blog industry trends

4. **Tool Integrations**
   - **Brainstorming**: Steps 02, 04 (domain exploration and creative ideation)
   - **Party Mode**: Steps 02, 03, 04, 05, 06 (multi-agent perspectives)
   - **Advanced Elicitation**: Steps 02, 03, 04, 05, 06, 07 (critical validation)
   - **Context-7**: Steps 06, 07 (library documentation and technical accuracy)

5. **Frontmatter Tracking**
   - stepsCompleted: Array tracking completed steps
   - lastStep: Name of last completed step
   - workflowComplete: Boolean marking final completion
   - domain: User's selected domain
   - exploredDomains: Historical tracking for sidecar memory
   - projectIdeas: Array of generated ideas
   - selectedIdea: Project name for deep-dive

### Output Document Structure

**File Name:** `opensource-project-spec-{project_name}.md`
**Location:** `{output_folder}/`

**Document Sections:**
1. Domain and Scope (Step 02)
2. Trend Analysis (Step 03)
3. Project Idea Candidates (Step 04)
4. Opportunity Ranking and Comparison (Step 05)
5. Deep-Dive Analysis (Step 06)
6. Technical Specification with 7 subsections (Step 07):
   - Project Overview and Value Proposition
   - Target Users and Use Cases
   - Core Features and Functionality
   - Technical Architecture and Stack Recommendations
   - Implementation Roadmap
   - Competitive Analysis
   - Success Metrics

### Quality Assurance

**Step File Validation:**
- ✅ All 8 step files created successfully
- ✅ Each step includes complete mandatory execution rules
- ✅ Proper path references using {variable} format
- ✅ Menu options correctly configured with handling logic
- ✅ Frontmatter update instructions included
- ✅ Success/failure metrics defined for each step
- ✅ Role reinforcement in every step
- ✅ Context boundaries clearly defined

**Workflow Integrity:**
- ✅ Step-to-step progression properly linked
- ✅ Continuation logic implemented (steps 01 and 01b)
- ✅ Final step (07) marked as FINAL with no next step
- ✅ All required tools properly integrated
- ✅ Web browsing capability emphasized in step 03
- ✅ Context-7 graceful fallback handling

**Documentation Completeness:**
- ✅ README includes installation instructions
- ✅ Usage guide covers all 7 steps
- ✅ Troubleshooting section for common issues
- ✅ Tips for best results included
- ✅ Context-7 noted as optional enhancement

### Workflow Characteristics

**Type:** Hybrid (Interactive + Document Generation + Research-Driven)
**Duration:** 2-4 sessions (research-intensive)
**User Engagement:** High collaboration with autonomous research phases
**Complexity:** Advanced (7 steps + continuation support + iterative features)
**Tools Required:** Web-browsing (ESSENTIAL), File I/O (REQUIRED)
**Tools Optional:** Context-7 (RECOMMENDED for technical accuracy)

### Invocation

**Command:**
```bash
/what-next-opensource
```

**First Run:** Loads step-01-init.md → Creates output document → Proceeds to step 02
**Continuation:** Loads step-01-init.md → Detects existing document → Routes to step-01b-continue.md → Resumes at appropriate step

### Build Completion

**Status:** ✅ Workflow creation complete and ready for use
**Files Generated:** 12 total (1 workflow.md, 1 README.md, 1 template, 8 step files, 1 workflow plan)
**Total Size:** ~97 KB of workflow documentation
**Architecture Compliance:** Fully compliant with BMAD step-file architecture standards
**User Testing:** Ready for first invocation

---

**Workflow created successfully on 2025-12-24 using BMAD BMB create-workflow system**