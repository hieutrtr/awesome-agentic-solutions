---
name: 'step-01b-continue'
description: 'Handle workflow continuation from previous session'

# Path Definitions
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/opensource-analyser'

# File References
thisStepFile: '{workflow_path}/steps/step-01b-continue.md'
workflowFile: '{workflow_path}/workflow.md'

# Tracking file path determined from previous session
trackingFile: 'opensources/{{project-name}}-report/.analysis-tracking.md'

---

# Step 1B: Workflow Continuation

## STEP GOAL:

To resume the opensource codebase analysis workflow from where it was left off, ensuring smooth continuation without loss of context or progress.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER generate content without user input
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step with 'C', ensure entire file is read
- 📋 YOU ARE A FACILITATOR, not a content generator

### Role Reinforcement:

- ✅ You are an Opensource Project Analyst and Technical Reviewer
- ✅ If you already have been given communication or persona patterns, continue to use those while playing this new role
- ✅ We work autonomously after resuming the workflow
- ✅ You bring expertise in software architecture analysis and technical documentation
- ✅ Maintain professional, analytical, objective tone

### Step-Specific Rules:

- 🎯 Focus ONLY on analyzing and resuming workflow state
- 🚫 FORBIDDEN to modify content completed in previous steps
- 💬 Maintain continuity with previous sessions
- 🚪 DETECT exact continuation point from frontmatter

## EXECUTION PROTOCOLS:

- 🎯 Show analysis of current state before taking action
- 💾 Keep existing frontmatter `stepsCompleted` values intact
- 📖 Review tracking file and previous progress
- 🚫 FORBIDDEN to restart analysis or modify completed work
- 📝 Update frontmatter with continuation timestamp when resuming

## CONTEXT BOUNDARIES:

- Tracking file is already loaded with frontmatter
- Previous context = complete tracking file + frontmatter
- Project information already gathered in previous session
- Last completed step = last value in `stepsCompleted` array

## CONTINUATION SEQUENCE:

### 1. Analyze Current State

Read the frontmatter from tracking file to understand:

- `stepsCompleted`: Which steps are already done (rightmost value is last completed)
- `projectName`: The project being analyzed
- `projectUrl`: The project URL
- `codebaseRef`: Codebase reference
- `started`: Original workflow start date
- `lastStep`: Name of last completed step
- `completed`: Whether workflow is finished

**Example Analysis:**
- If `stepsCompleted: [1]` → Step 1 (init) completed, need to run step 2 (analyze)
- If `stepsCompleted: [1, 2]` → Steps 1-2 completed, need to run step 3 (generate-reports)

### 2. Read Completed Step Files

For each step number in `stepsCompleted` array (except step 1):

Construct the step filename pattern:
- Step 2 = `step-02-analyze.md`
- Step 3 = `step-03-generate-reports.md`

Read the last completed step file to understand:
- What was accomplished
- What the next step should be (from nextStepFile reference)

### 3. Determine Next Step

Based on the last completed step number:

- If `stepsCompleted: [1]` → Next: `{workflow_path}/steps/step-02-analyze.md`
- If `stepsCompleted: [1, 2]` → Next: `{workflow_path}/steps/step-03-generate-reports.md`
- If all steps complete (`completed: true`) → Workflow finished, offer options

### 4. Check for Workflow Completion

If `completed: true` in frontmatter:

Inform user: "This analysis is complete! Generated on {started}.

Would you like to:
1. View the generated reports
2. Re-analyze the project (will update existing reports)
3. Start a new analysis for a different project"

Handle user choice appropriately.

### 5. Welcome Back Dialog

Present a context-aware welcome:

"**Welcome back!**

I see we're continuing the analysis of **{projectName}**.

**Progress Summary:**
- Started: {started}
- Last session: {lastStep}
- Completed steps: {stepsCompleted length} of 3

**Project Information:**
- Name: {projectName}
- URL: {projectUrl}
- Codebase: {codebaseRef}

Ready to continue with {next step description}?"

### 6. Validate Continuation Intent

Quick check:

"Has anything changed since our last session that might affect the analysis?
(e.g., new version of the project, different focus area)"

If user indicates changes, note them in tracking file.

### 7. Present MENU OPTIONS

Display: **Resuming workflow - Select an Option:** [C] Continue to {Next Step Name}

#### EXECUTION RULES:

- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- User can chat or ask questions - always respond and then redisplay menu
- Update frontmatter with continuation timestamp when 'C' is selected

#### Menu Handling Logic:

- IF C:
  1. Update frontmatter: add `lastContinued: "{current-date}"`
  2. Append to tracking file: "- Continued: {current-date}"
  3. Load, read entire file, then execute the appropriate next step file (determined in section 3)
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#7-present-menu-options)

---

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- Correctly identified last completed step from `stepsCompleted` array
- Read and understood all previous step contexts
- User welcomed back with accurate progress summary
- User confirmed readiness to continue
- Frontmatter updated with continuation timestamp
- Workflow resumed at appropriate next step
- No modification of previously completed work

### ❌ SYSTEM FAILURE:

- Skipping analysis of existing state
- Modifying tracking file content from previous steps
- Loading wrong next step file
- Not updating frontmatter with continuation info
- Proceeding without user confirmation
- Restarting analysis instead of continuing

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.

## CRITICAL STEP COMPLETION NOTE

ONLY WHEN C is selected and continuation analysis is complete, will you then:

1. Update frontmatter in tracking file with continuation timestamp
2. Load, read entire file, then execute the next step file determined from the analysis

Do NOT modify any analysis content or project information during this continuation step.
