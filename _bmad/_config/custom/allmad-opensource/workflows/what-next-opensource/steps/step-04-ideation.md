---
name: 'step-04-ideation'
description: 'Generate multiple project ideas iteratively'

<!-- Path Definitions -->
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/what-next-opensource'

# File References (all use {variable} format in file)
thisStepFile: '{workflow_path}/steps/step-04-ideation.md'
nextStepFile: '{workflow_path}/steps/step-05-ranking.md'
workflowFile: '{workflow_path}/workflow.md'
outputFile: '{output_folder}/opensource-project-spec-{project_name}.md'

# Task References
advancedElicitationTask: '{project-root}/_bmad/core/tasks/advanced-elicitation.xml'
partyModeWorkflow: '{project-root}/_bmad/core/workflows/party-mode/workflow.md'

---

# Step 4: Ideation

## STEP GOAL:
To generate multiple high-potential project ideas based on domain definition and trend analysis, allowing iterative exploration until the user has sufficient options to evaluate.

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
- ✅ You bring creative ideation and market analysis, user brings domain expertise and vision, and together we produce something better than we could on our own
- ✅ Maintain collaborative and creative tone throughout

### Step-Specific Rules:
- 🎯 Focus only on generating diverse project ideas based on trends
- 🚫 FORBIDDEN to evaluate or rank ideas yet (that comes in step 5)
- 💬 Approach: Creative and expansive - quantity and diversity over premature filtering
- 📋 Allow iterative ideation - user can request more ideas before proceeding

## EXECUTION PROTOCOLS:
- 🎯 Generate 3-5 project ideas per iteration based on trend analysis
- 💾 Accumulate all ideas in Project Ideas Candidates table
- 📖 Update output document with growing list of ideas
- 🚫 FORBIDDEN to proceed until user has sufficient ideas to choose from
- 🔄 Support [G] Generate More Ideas option for iterative exploration

## CONTEXT BOUNDARIES:
- Available context: Domain definition (step 2) and Trend Analysis (step 3) from {outputFile}
- Focus: Creative project ideation informed by research
- Limits: Don't rank or filter yet - generate options
- Dependencies: Trend analysis must provide insights for ideation

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read Current State

Read the output document at {outputFile} to:
- Retrieve the domain definition
- Review the complete trend analysis findings
- Check if any ideas have already been generated (from frontmatter `projectIdeas` array)
- Understand gaps, pain points, and opportunities identified

### 2. Announce Ideation Phase

Inform the user about the ideation approach:

"Now we'll generate project ideas based on the trends and opportunities we discovered in **[domain]**.

I'll create 3-5 distinct project concepts, each addressing different aspects of:
- Community pain points we identified
- Gaps in existing tools
- Emerging trends and opportunities
- Success patterns from popular projects

After reviewing these ideas, you can:
- Ask for more ideas if you want additional options
- Use Party Mode to get creative perspectives from other agents
- Proceed to ranking when you're ready to evaluate

Let me generate the first batch of ideas..."

### 3. Generate First Batch of Project Ideas

Based on trend analysis, generate 3-5 diverse project ideas.

For each idea, include:
- **Project Name** (creative, memorable)
- **One-line Description** (elevator pitch)
- **Problem It Solves** (specific pain point from research)
- **Target Users** (who benefits)
- **Key Differentiator** (what makes it unique)
- **Star Potential** (High/Medium/Low with brief justification)
- **Complexity** (Low/Medium/High - implementation difficulty)

Present ideas conversationally:

"Here are 5 project ideas based on our trend analysis:

**1. [Project Name]**
*[One-line description]*

**Problem It Solves:** [Pain point from research]
**Target Users:** [Specific audience]
**Key Differentiator:** [What makes it unique]
**Star Potential:** [High/Medium/Low - why?]
**Complexity:** [Low/Medium/High]

[Continue for ideas 2-5]

What are your initial thoughts on these directions?"

### 4. Gather User Feedback

Engage in conversation about the ideas:
- "Which of these resonate with you?"
- "Are there any directions here that don't align with your vision?"
- "Do you see opportunities we haven't explored yet?"

Listen to user feedback and adjust understanding.

### 5. Check if User Wants More Ideas

Ask explicitly:

"Would you like me to:
- Generate more project ideas (select [G] when I present the menu)
- Use Party Mode to get creative perspectives from other agents (select [P])
- Proceed to evaluating and ranking these ideas (select [C])

What would be most helpful?"

### 6. Document Current Ideas

Prepare the Project Ideas Candidates section (or append to existing if iterating):

```markdown
## Project Ideas Candidates

**Ideation Date:** [Current date]
**Ideas Generated:** [Current batch - e.g., "Batch 1" or "Batch 2"]

| # | Project Name | Description | Problem Solved | Target Users | Star Potential | Complexity |
|---|--------------|-------------|----------------|--------------|----------------|------------|
| 1 | [Name] | [One-liner] | [Problem] | [Users] | [H/M/L] | [L/M/H] |
| 2 | [Name] | [One-liner] | [Problem] | [Users] | [H/M/L] | [L/M/H] |
| 3 | [Name] | [One-liner] | [Problem] | [Users] | [H/M/L] | [L/M/H] |
| 4 | [Name] | [One-liner] | [Problem] | [Users] | [H/M/L] | [L/M/H] |
| 5 | [Name] | [One-liner] | [Problem] | [Users] | [H/M/L] | [L/M/H] |

### Detailed Ideas

[For each idea, provide expanded details:]

#### Idea 1: [Project Name]

**Elevator Pitch:** [One-line description]

**Problem It Solves:**
[Detailed explanation of the pain point, referencing specific findings from trend analysis]

**Target Users:**
[Description of primary audience and use cases]

**Key Features:**
- [Feature 1]
- [Feature 2]
- [Feature 3]

**Key Differentiator:**
[What makes this unique compared to existing solutions]

**Star Potential:** [High/Medium/Low]
[Justification based on similar projects, community demand, etc.]

**Implementation Complexity:** [Low/Medium/High]
[Brief explanation of technical scope]

[Repeat for each idea]
```

### 7. Update Output Document

Write or append to the Project Ideas Candidates section in {outputFile}:
- Add new ideas to the table (maintain all previous ideas if this is iteration 2+)
- Include detailed breakdowns for all ideas
- Update frontmatter: `projectIdeas` array with list of idea names
- Update frontmatter: `lastStep: 'ideation'`
- Update frontmatter: `stepsCompleted` to include 4 if not already present

### 8. Present MENU OPTIONS

Display: "**Select an Option:** [A] Advanced Elicitation [P] Party Mode [G] Generate More Ideas [C] Continue to Ranking"

#### Menu Handling Logic:
- IF A: Execute {advancedElicitationTask} with context: "Review the project ideas for overlooked opportunities, alternative angles, or more innovative concepts"
- IF P: Execute {partyModeWorkflow} with context: "Get diverse creative perspectives on these project ideas or generate new concepts"
- IF G:
  1. Loop back to step 3 (Generate First Batch) to create 3-5 MORE ideas
  2. Accumulate new ideas with existing ones in the document
  3. Return to this menu after documenting new ideas
  4. DO NOT mark step as complete again - continue ideation loop
- IF C: Save all ideas to {outputFile}, update frontmatter with stepsCompleted: [1, 2, 3, 4], then only then load, read entire file, then execute {nextStepFile}
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#8-present-menu-options)

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- [G] option creates an ideation loop - can be selected multiple times
- ONLY proceed to next step when user selects 'C'
- After other menu items execution completes, redisplay the menu
- User can chat or ask questions - always respond and then end with display again of the menu options

## CRITICAL STEP COMPLETION NOTE

Ideation must generate sufficient project ideas for evaluation:
- Minimum 3 project ideas documented (preferably 5+)
- All ideas include complete details (problem, users, features, differentiator, star potential, complexity)
- Project Ideas Candidates section written to {outputFile}
- Frontmatter updated with projectIdeas array and stepsCompleted: [1, 2, 3, 4]
- User has selected [C] to continue (not [G] for more ideas)

ONLY WHEN [C continue option] is selected and sufficient ideas are documented, will you then load and read fully `{nextStepFile}` to execute and begin ranking.

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- 3-5 diverse project ideas generated per batch
- All ideas directly address findings from trend analysis
- Each idea includes complete details (name, description, problem, users, differentiator, star potential, complexity)
- Ideas span different approaches and complexity levels
- User feedback incorporated into understanding
- Iterative ideation supported through [G] option
- Project Ideas Candidates section written to output document
- Frontmatter updated with complete idea list
- User satisfied with quantity and diversity before proceeding

### ❌ SYSTEM FAILURE:
- Generating fewer than 3 ideas without user agreement
- Ideas not grounded in trend analysis findings
- Evaluating or ranking ideas prematurely (that's step 5)
- Proceeding to ranking without sufficient options
- Not supporting iterative ideation through [G] option
- Not accumulating all ideas across iterations
- Missing key details for any idea

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
