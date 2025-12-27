---
name: 'step-05-ranking'
description: 'Compare and rank project opportunities'

<!-- Path Definitions -->
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/what-next-opensource'

# File References (all use {variable} format in file)
thisStepFile: '{workflow_path}/steps/step-05-ranking.md'
nextStepFile: '{workflow_path}/steps/step-06-deep-dive.md'
workflowFile: '{workflow_path}/workflow.md'
outputFile: '{output_folder}/opensource-project-spec-{project_name}.md'

# Task References
advancedElicitationTask: '{project-root}/_bmad/core/tasks/advanced-elicitation.xml'
partyModeWorkflow: '{project-root}/_bmad/core/workflows/party-mode/workflow.md'

---

# Step 5: Ranking

## STEP GOAL:
To systematically evaluate and rank all project ideas using objective criteria, helping the user select the top 1-2 ideas for deep-dive analysis.

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
- ✅ You bring analytical evaluation and market insights, user brings personal priorities and decision-making, and together we produce something better than we could on our own
- ✅ Maintain collaborative and analytical tone throughout

### Step-Specific Rules:
- 🎯 Focus only on objective evaluation and ranking of ideas
- 🚫 FORBIDDEN to conduct deep research yet (that comes in step 6)
- 💬 Approach: Systematic comparison using defined criteria
- 📋 User makes final selection of top ideas for deep-dive

## EXECUTION PROTOCOLS:
- 🎯 Evaluate all ideas against 4 key criteria
- 💾 Create comparison matrix with scores and justifications
- 📖 Update output document with Ranking Analysis section
- 🚫 FORBIDDEN to proceed until user selects top ideas for deep-dive

## CONTEXT BOUNDARIES:
- Available context: All project ideas from step 4 in {outputFile}
- Focus: Systematic evaluation and ranking
- Limits: Surface-level comparison - deep research comes in step 6
- Dependencies: Minimum 3 project ideas must exist from step 4

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read Current State

Read the output document at {outputFile} to:
- Retrieve all project ideas from step 4
- Count total number of ideas to rank
- Review trend analysis to inform evaluation criteria
- Check frontmatter `projectIdeas` array

### 2. Introduce Ranking Framework

Explain the evaluation approach to the user:

"We now have [X] project ideas to evaluate. Let's systematically compare them using four key criteria:

1. **Star Potential** - Likelihood of gaining community traction and GitHub stars
   - Based on similar project success, community demand, trending topics

2. **Feasibility** - How realistic is it to build and maintain this project?
   - Technical complexity, time required, dependencies, your expertise

3. **Differentiation** - How unique is this compared to existing solutions?
   - Gap analysis from our trend research, competitive advantages

4. **Market Demand** - How strong is the validated need for this?
   - Pain points from community research, Stack Overflow questions, discussion volume

I'll evaluate each idea on a scale of 1-5 for each criterion, then we'll discuss which ideas are most compelling to you."

### 3. Create Comparison Matrix

Evaluate each project idea against the four criteria:

For each idea, assign scores (1-5) with brief justification:
- **Star Potential:** [1-5] - [why?]
- **Feasibility:** [1-5] - [why?]
- **Differentiation:** [1-5] - [why?]
- **Market Demand:** [1-5] - [why?]
- **Total Score:** [sum of all scores]

Present the matrix to the user:

```
## Comparison Matrix

| Project | Star Potential | Feasibility | Differentiation | Market Demand | Total |
|---------|----------------|-------------|-----------------|---------------|-------|
| Idea 1  | 4              | 3           | 5               | 4             | 16    |
| Idea 2  | 5              | 2           | 3               | 5             | 15    |
| [etc]   | ...            | ...         | ...             | ...           | ...   |
```

### 4. Provide Detailed Evaluation

For each idea, explain the scoring:

"**Idea 1: [Project Name]**

**Star Potential: [Score]/5**
[Justification based on similar projects, community interest, trending topics]

**Feasibility: [Score]/5**
[Justification based on technical complexity, time, your expertise]

**Differentiation: [Score]/5**
[Justification based on existing solutions, unique value proposition]

**Market Demand: [Score]/5**
[Justification based on pain points, community discussions, validation]

**Overall Assessment:**
[Synthesized view of strengths and weaknesses]

---

[Repeat for all ideas]"

### 5. Present Ranked Results

Show the ranked list and open discussion:

"**Ranked Project Ideas:**

1. [Project Name] - [Total Score] - [Key strength]
2. [Project Name] - [Total Score] - [Key strength]
3. [Project Name] - [Total Score] - [Key strength]
[Continue for all ideas]

These rankings are based on objective criteria, but your personal priorities matter most. Some questions to consider:

- Which ideas align best with your technical strengths?
- Which problems are you most passionate about solving?
- Which projects would you be most excited to maintain long-term?
- Are there any lower-ranked ideas that still resonate strongly with you?

What are your thoughts on these rankings?"

### 6. Facilitate Selection Discussion

Engage in dialogue to help user select top ideas:

"For the next step, we'll conduct deep-dive analysis on 1-2 projects. This will include:
- Detailed competitive analysis
- Feature planning
- Architecture considerations
- Go-to-market strategy

Which 1-2 ideas would you like to explore in depth?"

Wait for user selection. Validate their choice:
- If user selects 1 idea: Confirm and proceed
- If user selects 2 ideas: Confirm and proceed
- If user selects 3+ ideas: Gently suggest focusing on 1-2 for depth
- If user disagrees with rankings: Discuss and adjust understanding

### 7. Document Ranking Analysis

Prepare the Ranking Analysis section:

```markdown
## Ranking Analysis

**Evaluation Date:** [Current date]
**Total Ideas Evaluated:** [Number]

### Evaluation Criteria

1. **Star Potential (1-5)** - Likelihood of gaining community traction and GitHub stars
2. **Feasibility (1-5)** - Realistic to build and maintain given constraints
3. **Differentiation (1-5)** - Uniqueness compared to existing solutions
4. **Market Demand (1-5)** - Strength of validated need from research

### Comparison Matrix

| Project | Star Potential | Feasibility | Differentiation | Market Demand | Total Score |
|---------|----------------|-------------|-----------------|---------------|-------------|
| [Idea 1] | [score] | [score] | [score] | [score] | [total] |
| [Idea 2] | [score] | [score] | [score] | [score] | [total] |
| [etc] | ... | ... | ... | ... | ... |

### Detailed Evaluations

[For each idea, include complete evaluation breakdown with justifications]

#### [Project Name 1]
- **Star Potential:** [Score]/5 - [Justification]
- **Feasibility:** [Score]/5 - [Justification]
- **Differentiation:** [Score]/5 - [Justification]
- **Market Demand:** [Score]/5 - [Justification]
- **Overall Assessment:** [Summary]

[Repeat for all ideas]

### Final Rankings

1. **[Project Name]** - [Total Score]/20 - [Key insight]
2. **[Project Name]** - [Total Score]/20 - [Key insight]
3. **[Project Name]** - [Total Score]/20 - [Key insight]
[Continue for all ideas]

### Selected for Deep-Dive

**Primary Selection:** [Project Name]
**Secondary Selection (if applicable):** [Project Name or "None"]

**User's Rationale:**
[Why user selected these ideas over others]
```

### 8. Update Output Document

Write the Ranking Analysis section to {outputFile}:
- Add the complete section after Project Ideas Candidates
- Update frontmatter: `selectedIdea: "[primary project name]"`
- Update frontmatter: `lastStep: 'ranking'`
- Ensure `stepsCompleted` array now includes: `[1, 2, 3, 4, 5]`

### 9. Present MENU OPTIONS

Display: "**Select an Option:** [A] Advanced Elicitation [P] Party Mode [C] Continue to Deep-Dive"

#### Menu Handling Logic:
- IF A: Execute {advancedElicitationTask} with context: "Review the ranking analysis for alternative perspectives, overlooked factors, or different prioritization approaches"
- IF P: Execute {partyModeWorkflow} with context: "Get diverse perspectives on which project ideas have the most potential"
- IF C: Save content to {outputFile}, update frontmatter, then only then load, read entire file, then execute {nextStepFile}
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#9-present-menu-options)

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- After other menu items execution completes, redisplay the menu
- User can chat or ask questions - always respond and then end with display again of the menu options

## CRITICAL STEP COMPLETION NOTE

Ranking analysis must be complete and user must select top ideas:
- All project ideas evaluated against 4 criteria with scores and justifications
- Comparison matrix created with total scores
- Ranked list presented
- User has selected 1-2 ideas for deep-dive analysis
- Ranking Analysis section written to {outputFile}
- Frontmatter updated with selectedIdea and stepsCompleted: [1, 2, 3, 4, 5]
- User has selected [C] to continue

ONLY WHEN [C continue option] is selected and ranking is complete with user selection, will you then load and read fully `{nextStepFile}` to execute and begin deep-dive analysis.

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- All project ideas systematically evaluated against 4 criteria
- Each score includes clear justification grounded in research
- Comparison matrix created with total scores
- Ranked list presented in order
- User engaged in selection discussion
- User selected 1-2 ideas for deep-dive (documented their rationale)
- Ranking Analysis section written to output document
- Frontmatter updated with selectedIdea and step completion
- Ready to proceed to deep-dive with clear direction

### ❌ SYSTEM FAILURE:
- Evaluating ideas without clear scoring criteria
- Scores without justifications or arbitrary ratings
- Making selection decision for the user
- Proceeding without user confirmation of selected ideas
- Not documenting user's rationale for selection
- Skipping comparison matrix or detailed evaluations

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
