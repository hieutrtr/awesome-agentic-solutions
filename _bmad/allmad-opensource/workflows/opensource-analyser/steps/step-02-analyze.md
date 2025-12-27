---
name: 'step-02-analyze'
description: 'Perform comprehensive codebase analysis using web browsing, file I/O, and specialized sub-agents'

# Path Definitions
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/opensource-analyser'

# File References
thisStepFile: '{workflow_path}/steps/step-02-analyze.md'
nextStepFile: '{workflow_path}/steps/step-03-generate-reports.md'
workflowFile: '{workflow_path}/workflow.md'

# Tracking file from initialization
trackingFile: 'opensources/{{project-name}}-report/.analysis-tracking.md'

# Task References
advancedElicitationTask: '{project-root}/_bmad/core/tasks/advanced-elicitation.xml'
partyModeWorkflow: '{project-root}/_bmad/core/workflows/party-mode/workflow.md'

---

# Step 2: Codebase Analysis

## STEP GOAL:

To perform comprehensive codebase analysis by gathering project information, inspecting the codebase, and deploying specialized sub-agents for parallel analysis of technology stack, architecture, use cases, pros/cons, and alternatives.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER generate content without user input (exception: autonomous analysis in this step)
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step with 'C', ensure entire file is read
- 📋 YOU ARE A FACILITATOR AND ANALYST

### Role Reinforcement:

- ✅ You are an Opensource Project Analyst and Technical Reviewer
- ✅ If you already have been given communication or persona patterns, continue to use those while playing this new role
- ✅ You work autonomously during analysis phase
- ✅ You bring expertise in software architecture, technology evaluation, and comparative analysis
- ✅ Maintain professional, analytical, objective, evidence-based tone

### Step-Specific Rules:

- 🎯 Focus ONLY on analysis and data gathering
- 🚫 FORBIDDEN to generate reports in this step (that's step 3)
- 💬 Work autonomously but update user on progress
- 🔍 Use all available tools: Web-Browsing, File I/O, Sub-Agents, Sub-Processes

## EXECUTION PROTOCOLS:

- 🎯 Perform systematic analysis across all dimensions
- 💾 Store all findings in tracking file for report generation
- 📖 Update frontmatter `stepsCompleted: [1, 2]` before loading next step
- 🚫 FORBIDDEN to load next step until analysis is complete and user approves

## CONTEXT BOUNDARIES:

- Project information from tracking file frontmatter is available
- projectName, projectUrl, codebaseRef are known
- This step gathers ALL data needed for reports
- Analysis findings stored in tracking file for step 3

## ANALYSIS SEQUENCE:

### 1. Load Project Context

Read tracking file to retrieve:
- `projectName`: Project being analyzed
- `projectUrl`: URL to project repository/site
- `codebaseRef`: Reference to codebase for inspection

Display:
"**Starting Analysis: {projectName}**

Analyzing codebase from: {codebaseRef}
Documentation from: {projectUrl}

This will involve:
1. Project information gathering (web browsing)
2. Codebase inspection (file analysis)
3. Parallel specialized analysis (sub-agents)
4. Findings synthesis

Beginning analysis..."

### 2. Project Information Gathering (Web-Browsing)

Use WebSearch and WebFetch to gather:

**A. Repository Metadata:**
- GitHub stars, forks, watchers (if GitHub)
- Number of contributors
- Open/closed issues count
- Latest release version and date
- License information
- Primary programming language(s)

**B. Documentation Access:**
- README content
- Official documentation site
- Getting started guides
- API documentation availability

**C. Community Metrics:**
- Community activity level
- Recent commit frequency
- Issue response time patterns
- Discussion forum activity (if applicable)

**D. Ecosystem Information:**
- Related projects and integrations
- Plugin/extension ecosystem
- Known adopters or use cases
- Comparison with similar projects

Progress Update: "Gathered project metadata and community insights."

### 3. Codebase Inspection (File I/O)

Access and analyze the codebase:

**A. Key Files Analysis:**
- README.md (project description, features)
- package.json / requirements.txt / Cargo.toml (dependencies)
- LICENSE (licensing terms)
- CONTRIBUTING.md (contribution guidelines)
- Configuration files (identify frameworks/tools)

**B. Directory Structure:**
- Analyze folder organization
- Identify main source directories
- Locate test directories
- Find documentation folders

**C. Code Sample Inspection:**
- Review main entry points
- Examine core modules/components
- Identify design patterns used
- Check code organization style

**D. Dependency Analysis:**
- List major dependencies
- Identify framework choices
- Note build tools and dev dependencies

Progress Update: "Completed codebase inspection."

### 4. Parallel Specialized Analysis (Sub-Agents)

Deploy specialized sub-agents for concurrent analysis:

**Sub-Agent 1: Tech Stack Agent**
Task: Identify and document complete technology stack
- Programming languages (primary and secondary)
- Frameworks and libraries
- Build tools and package managers
- Development tools and testing frameworks
- Database technologies (if applicable)
- CI/CD and deployment tools

**Sub-Agent 2: Architecture Agent**
Task: Analyze architectural patterns and decisions
- Overall architecture style (monolith, microservices, serverless, etc.)
- Design patterns employed
- Code organization principles
- Module/component structure
- API design approach
- Data flow patterns

**Sub-Agent 3: Use Cases Agent**
Task: Determine primary use cases and target users
- Main problem solved
- Primary use cases (top 3-5)
- Target user personas
- Common application scenarios
- Industry/domain applicability
- Typical deployment contexts

**Sub-Agent 4: Evaluation Agent**
Task: Assess strengths, weaknesses, and performance characteristics
- Strengths (pros):
  - Technical advantages
  - Developer experience benefits
  - Performance characteristics
  - Community and ecosystem strengths
- Weaknesses (cons):
  - Technical limitations
  - Learning curve challenges
  - Potential performance issues
  - Ecosystem gaps
- Performance considerations:
  - Scalability characteristics
  - Resource requirements
  - Known bottlenecks

**Sub-Agent 5: Alternatives Agent**
Task: Research competing and similar projects
- Identify 3-5 main alternatives
- For each alternative:
  - Project name and description
  - Similarities to analyzed project
  - Key differences
  - When to choose this alternative vs the analyzed project
  - Relative popularity/maturity

Progress Update: "Specialized analysis complete. Synthesizing findings..."

### 5. Synthesis and Storage

Compile all findings from sub-agents into structured format.

Append to tracking file:

```markdown
## Analysis Findings

### Project Metadata
[Repository metrics, version, license, activity]

### Technology Stack
[Complete stack from Tech Stack Agent]

### Architecture Analysis
[Architecture patterns and decisions from Architecture Agent]

### Use Cases
[Primary use cases and target users from Use Cases Agent]

### Evaluation
**Strengths:**
[Pros from Evaluation Agent]

**Weaknesses:**
[Cons from Evaluation Agent]

**Performance Characteristics:**
[Performance notes from Evaluation Agent]

### Alternatives
[Competing projects with comparisons from Alternatives Agent]

### Code Quality Observations
[Code organization, documentation quality, test coverage notes]

### Community and Maintenance
[Community activity, maintenance status, ecosystem health]
```

Update frontmatter in tracking file:
```yaml
stepsCompleted: [1, 2]
lastStep: "Codebase Analysis"
analysisCompleted: "{current-date}"
```

### 6. Present Analysis Summary

Display summary:

"**Analysis Complete!**

I've gathered comprehensive data about {projectName}:

✅ Project metadata and community metrics
✅ Technology stack identification
✅ Architecture analysis
✅ Use case determination
✅ Strengths and weaknesses evaluation
✅ Alternative solutions research
✅ Code quality observations

All findings have been stored and are ready for report generation.

The next step will generate:
- overview.md (quick summary)
- detailed-report.md (comprehensive analysis)"

### 7. Present MENU OPTIONS

Display: **Select an Option:** [A] Advanced Elicitation [P] Party Mode [C] Continue to Report Generation

#### EXECUTION RULES:

- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- After other menu items execution, return to this menu
- User can chat or ask questions - always respond and then redisplay menu

#### Menu Handling Logic:

- IF A: Execute {advancedElicitationTask} to explore alternative analysis approaches or findings
- IF P: Execute {partyModeWorkflow} to get additional perspectives on the analysis
- IF C: Verify analysis is stored in tracking file, update frontmatter, then load, read entire file, then execute {nextStepFile} (step-03-generate-reports.md)
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#7-present-menu-options)

---

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- All project metadata gathered from web sources
- Codebase inspected and key files analyzed
- All 5 sub-agents completed their specialized analysis tasks
- Findings synthesized and stored in tracking file
- Frontmatter updated with stepsCompleted: [1, 2]
- User presented with analysis summary
- Ready to proceed to report generation

### ❌ SYSTEM FAILURE:

- Skipping web browsing or codebase inspection
- Not deploying all sub-agents
- Incomplete analysis in any dimension
- Not storing findings in tracking file
- Proceeding without user approval via menu
- Not updating frontmatter

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.

## CRITICAL STEP COMPLETION NOTE

ONLY WHEN C is selected and all analysis findings are stored in tracking file, will you then load, read entire file, then execute `{nextStepFile}` (step-03-generate-reports.md) to begin report generation.
