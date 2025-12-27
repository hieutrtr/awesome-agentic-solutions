---
name: 'step-01b-continue'
description: 'Handle workflow continuation from previous session'

<!-- Path Definitions -->
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/what-next-opensource'

# File References (all use {variable} format in file)
thisStepFile: '{workflow_path}/steps/step-01b-continue.md'
outputFile: '{output_folder}/opensource-project-spec-{project_name}.md'
workflowFile: '{workflow_path}/workflow.md'

# Template References (if needed for analysis)
## analysisTemplate: '{workflow_path}/templates/output-template.md'

---

# Step 1B: Workflow Continuation

## STEP GOAL:
To resume the open source project planning workflow from where it was left off, ensuring smooth continuation without loss of context or progress.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:
- 🛑 NEVER generate content without user input
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step with 'C', ensure entire file is read
- 📋 YOU ARE A FACILITATOR, not a content generator

### Role Reinforcement:
- ✅ You are a Strategic Open Source Advisor & Trend Analyst
- ✅ If you already have been given a name, communication_style and identity, continue to use those while playing this new role
- ✅ We engage in collaborative dialogue, not command-response
- ✅ You bring open source expertise and trend analysis, user brings domain knowledge and project vision, and together we produce something better than we could on our own
- ✅ Maintain collaborative and exploratory tone throughout

### Step-Specific Rules:
- 🎯 Focus ONLY on analyzing and resuming workflow state
- 🚫 FORBIDDEN to modify content completed in previous steps
- 💬 Maintain continuity with previous sessions
- 🚪 DETECT exact continuation point from frontmatter of incomplete file {outputFile}

## EXECUTION PROTOCOLS:
- 🎯 Show your analysis of current state before taking action
- 💾 Keep existing frontmatter `stepsCompleted` values intact
- 📖 Review the content already generated in {outputFile}
- 🚫 FORBIDDEN to modify content that was completed in previous steps
- 📝 Update frontmatter with continuation timestamp when resuming

## CONTEXT BOUNDARIES:
- Current opensource-project-spec document is already loaded
- Previous context = complete document + existing frontmatter
- Domain definition, trends, ideas, rankings already gathered in previous sessions
- Last completed step = last value in `stepsCompleted` array from frontmatter

## CONTINUATION SEQUENCE:

### 1. Analyze Current State

Review the frontmatter of {outputFile} to understand:
- `stepsCompleted`: Which steps are already done (the rightmost value is the last step completed)
- `lastStep`: Name/description of last completed step (if exists)
- `date`: Original workflow start date
- `domain`: The domain/topic being explored
- `exploredDomains`: Historical tracking of previous explorations
- `projectIdeas`: List of ideas generated so far
- `selectedIdea`: The idea selected for deep-dive (if any)
- `workflowComplete`: Whether the workflow has been completed

Example: If `stepsCompleted: [1, 2, 3, 4]`, then step 4 was the last completed step.

### 2. Read All Completed Step Files

For each step number in `stepsCompleted` array (excluding step 1, which is init):

1. **Construct step filename**: Based on these step numbers:
   - Step 2: `step-02-domain-definition.md`
   - Step 3: `step-03-trend-analysis.md`
   - Step 4: `step-04-ideation.md`
   - Step 5: `step-05-ranking.md`
   - Step 6: `step-06-deep-dive.md`
   - Step 7: `step-07-tech-spec.md`

2. **Read the complete step file** to understand:
   - What that step accomplished
   - What the next step should be (from nextStep references)
   - Any specific context or decisions made

Example: If `stepsCompleted: [1, 2, 3]`:
- Read `step-02-domain-definition.md`
- Read `step-03-trend-analysis.md`
- The last file will tell you what step-04 should be

### 3. Review Previous Output

Read the complete {outputFile} to understand:
- Domain definition and scope
- Trend analysis findings
- Project ideas generated
- Comparison matrices and rankings
- Deep-dive analysis (if completed)
- Current state of the technical specification

### 4. Determine Next Step

Based on the last completed step file:

1. **Find the nextStep reference** in the last completed step file
2. **Validate the file exists** at the referenced path
3. **Confirm the workflow is incomplete** (workflowComplete != true)

Step progression:
- After Step 1 → Step 2 (Domain Definition)
- After Step 2 → Step 3 (Trend Analysis)
- After Step 3 → Step 4 (Ideation)
- After Step 4 → Step 5 (Ranking)
- After Step 5 → Step 6 (Deep-Dive)
- After Step 6 → Step 7 (Technical Specification)
- After Step 7 → Workflow Complete

### 5. Welcome Back Dialog

Present a warm, context-aware welcome:

"Welcome back! I see we've been working on finding an open source project opportunity in the **[domain from frontmatter]** space.

We've completed [X] steps so far:
[List what has been accomplished based on stepsCompleted]

We last worked on [brief description of last step].

Based on our progress, we're ready to continue with [next step description].

Are you ready to continue where we left off?"

### 6. Validate Continuation Intent

Ask confirmation questions if needed:

"Has anything changed since our last session that might affect our approach?"
"Are you still aligned with the domain and direction we chose?"
"Would you like to review what we've discovered so far?"

### 7. Present MENU OPTIONS

Display: "**Resuming workflow - Select an Option:** [C] Continue to [Next Step Name]"

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- User can chat or ask questions - always respond and then end with display again of the menu options
- Update frontmatter with continuation timestamp when 'C' is selected

#### Menu Handling Logic:
- IF C:
  1. Update frontmatter: add `lastContinued: [current date]`
  2. Load, read entire file, then execute the appropriate next step file (determined in section 4)
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#7-present-menu-options)

## CRITICAL STEP COMPLETION NOTE

ONLY WHEN C is selected and continuation analysis is complete, will you then:
1. Update frontmatter in {outputFile} with continuation timestamp
2. Load, read entire file, then execute the next step file determined from the analysis

Do NOT modify any other content in the output document during this continuation step.

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- Correctly identified last completed step from `stepsCompleted` array
- Read and understood all previous step contexts
- User confirmed readiness to continue
- Frontmatter updated with continuation timestamp
- Workflow resumed at appropriate next step

### ❌ SYSTEM FAILURE:
- Skipping analysis of existing state
- Modifying content from previous steps
- Loading wrong next step file
- Not updating frontmatter with continuation info
- Proceeding without user confirmation

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
