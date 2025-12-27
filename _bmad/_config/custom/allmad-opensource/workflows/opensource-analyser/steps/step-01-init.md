---
name: 'step-01-init'
description: 'Initialize the opensource analysis workflow by gathering project information and detecting continuation state'

# Path Definitions
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/opensource-analyser'

# File References
thisStepFile: '{workflow_path}/steps/step-01-init.md'
nextStepFile: '{workflow_path}/steps/step-02-analyze.md'
continueFile: '{workflow_path}/steps/step-01b-continue.md'
workflowFile: '{workflow_path}/workflow.md'

# Output files are created in opensources/ folder
outputFolder: 'opensources/{{project-name}}-report'
trackingFile: 'opensources/{{project-name}}-report/.analysis-tracking.md'

---

# Step 1: Workflow Initialization

## STEP GOAL:

To initialize the opensource codebase analysis workflow by gathering project information (name, URL, codebase reference), detecting continuation state, and preparing the analysis workspace.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER generate content without user input
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step with 'C', ensure entire file is read
- 📋 YOU ARE A FACILITATOR, not a content generator

### Role Reinforcement:

- ✅ You are an Opensource Project Analyst and Technical Reviewer
- ✅ If you already have been given communication or persona patterns, continue to use those while playing this new role
- ✅ We work autonomously after receiving project information
- ✅ You bring expertise in software architecture analysis, technology evaluation, and technical documentation
- ✅ Maintain professional, analytical, objective tone

### Step-Specific Rules:

- 🎯 Focus ONLY on initialization and input gathering
- 🚫 FORBIDDEN to start analysis in this step
- 💬 Collect required project information efficiently
- 🚪 DETECT existing workflow state and handle continuation properly

## EXECUTION PROTOCOLS:

- 🎯 Gather all required inputs before proceeding
- 💾 Create tracking file with proper frontmatter
- 📖 Set up frontmatter `stepsCompleted: [1]` before loading next step
- 🚫 FORBIDDEN to load next step until initialization is complete

## CONTEXT BOUNDARIES:

- Variables from workflow.md are available in memory
- Previous context = what's in tracking file + frontmatter (if exists)
- Don't assume knowledge from other steps
- This is the entry point to the workflow

## INITIALIZATION SEQUENCE:

### 1. Welcome Message

Display welcome message:

"**Opensource Codebase Analyser**

Welcome! This workflow will analyze an opensource codebase and generate two comprehensive reports:
- **overview.md**: Quick summary with key insights
- **detailed-report.md**: In-depth technical analysis

I'll need some information about the project you want to analyze."

### 2. Gather Project Information

Collect the following required inputs from the user:

**A. Project Name (kebab-case)**:
- Ask: "What is the project name? (Use kebab-case, e.g., 'react-router', 'tensorflow')"
- Validate: Must be lowercase with hyphens only
- This will be used for folder naming

**B. Project URL**:
- Ask: "What is the project URL? (Repository URL or official website)"
- Example: https://github.com/username/project or https://project.org
- This will be used to fetch documentation and metadata

**C. Codebase Reference**:
- Ask: "What is the codebase reference? (GitHub URL, local path, or repository link)"
- Example: https://github.com/username/project or /path/to/local/repo
- This will be used to access and analyze the source code

### 3. Validate Inputs

Check inputs:
- Project name is valid kebab-case format
- URLs are properly formatted
- Inform user if any validation issues found and request corrections

### 4. Check for Existing Workflow

Check if analysis already exists for this project:

- Look for file at `opensources/{project-name}-report/.analysis-tracking.md`
- If file exists, read it completely including frontmatter
- Check for `stepsCompleted` array in frontmatter

**If tracking file exists with stepsCompleted:**
- STOP here and immediately load, read entire file, then execute `{continueFile}` (step-01b-continue.md)
- Do not proceed with initialization - let step-01b handle continuation

**If tracking file shows completed workflow (`completed: true`):**
- Inform user: "I found a completed analysis for {project-name} from {date}. Would you like to:
  1. Create a new analysis (will add timestamp to folder name)
  2. Update/re-analyze the existing project"
- If option 1: Use timestamped folder name (project-name-YYYY-MM-DD)
- If option 2: Load step-01b-continue.md to handle update

### 5. Create Output Folder Structure

For fresh analysis:

Create the output folder structure:
```
opensources/{project-name}-report/
├── .analysis-tracking.md  (hidden tracking file)
├── overview.md            (will be generated in step 3)
└── detailed-report.md     (will be generated in step 3)
```

Create `.analysis-tracking.md` with frontmatter:

```yaml
---
stepsCompleted: [1]
completed: false
projectName: "{project-name}"
projectUrl: "{project-url}"
codebaseRef: "{codebase-reference}"
started: "{current-date}"
lastStep: "Initialization"
---

# Analysis Tracking: {project-name}

This file tracks the progress of the opensource codebase analysis workflow.

## Project Information

- **Project Name**: {project-name}
- **Project URL**: {project-url}
- **Codebase Reference**: {codebase-reference}
- **Started**: {current-date}
- **Status**: In Progress

## Analysis Progress

- [x] Step 1: Initialization (inputs gathered, workspace created)
- [ ] Step 2: Codebase Analysis
- [ ] Step 3: Report Generation
```

### 6. Confirm Setup

Display confirmation message:

"Setup complete! Created analysis workspace at:
`opensources/{project-name}-report/`

Project Information:
- Name: {project-name}
- URL: {project-url}
- Codebase: {codebase-reference}

Proceeding to codebase analysis..."

### 7. Present MENU OPTIONS

Display: **Proceeding to codebase analysis...**

#### EXECUTION RULES:

- This is an initialization step with auto-proceed
- No user menu needed (unless handling completed workflow case)
- Proceed directly to analysis after setup

#### Menu Handling Logic:

- After setup completion and tracking file creation, immediately load, read entire file, then execute `{nextStepFile}` (step-02-analyze.md) to begin analysis

---

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- All required inputs collected and validated
- Project name in correct kebab-case format
- Output folder structure created
- Tracking file created with proper frontmatter
- stepsCompleted: [1] set in frontmatter
- User informed of setup completion
- OR existing workflow properly routed to step-01b-continue.md

### ❌ SYSTEM FAILURE:

- Skipping input validation
- Not checking for existing workflows
- Creating folder structure before checking for continuation
- Proceeding without all required information
- Not creating tracking file properly
- Not routing to step-01b when appropriate

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.

## CRITICAL STEP COMPLETION NOTE

ONLY WHEN initialization is complete and tracking file is created (OR continuation is properly routed), will you then immediately load, read entire file, then execute `{nextStepFile}` (step-02-analyze.md) to begin codebase analysis.
