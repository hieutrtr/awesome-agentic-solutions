---
name: 'step-06-deep-dive'
description: 'Deep-dive analysis of selected project idea(s)'

<!-- Path Definitions -->
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/what-next-opensource'

# File References (all use {variable} format in file)
thisStepFile: '{workflow_path}/steps/step-06-deep-dive.md'
nextStepFile: '{workflow_path}/steps/step-07-tech-spec.md'
workflowFile: '{workflow_path}/workflow.md'
outputFile: '{output_folder}/opensource-project-spec-{project_name}.md'

# Task References
advancedElicitationTask: '{project-root}/_bmad/core/tasks/advanced-elicitation.xml'
partyModeWorkflow: '{project-root}/_bmad/core/workflows/party-mode/workflow.md'

---

# Step 6: Deep-Dive Analysis

## STEP GOAL:
To conduct comprehensive deep-dive analysis on the selected project idea(s), including competitive analysis, feature planning, architecture considerations, and validation of market positioning.

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
- ✅ You bring competitive analysis and technical planning expertise, user brings product vision and validation, and together we produce something better than we could on our own
- ✅ Maintain collaborative and thorough tone throughout

### Step-Specific Rules:
- 🎯 Focus only on deep analysis of selected idea(s)
- 🚫 FORBIDDEN to write final technical spec yet (that comes in step 7)
- 💬 Approach: Thorough research and critical validation
- 📋 Use Advanced Elicitation to challenge assumptions and find gaps

## EXECUTION PROTOCOLS:
- 🎯 Conduct detailed competitive analysis with web research
- 💾 Define comprehensive feature set with prioritization
- 📖 Explore architecture options (optionally using Context-7)
- 🚫 FORBIDDEN to proceed until deep analysis is validated

## CONTEXT BOUNDARIES:
- Available context: Selected idea(s) from step 5 in {outputFile}
- Focus: Deep competitive and technical analysis
- Limits: Analysis and planning - final spec synthesis in step 7
- Dependencies: User must have selected 1-2 ideas in step 5

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read Current State

Read the output document at {outputFile} to:
- Retrieve the selected project idea from frontmatter `selectedIdea`
- Review the full project idea details from step 4
- Review ranking justification from step 5
- Understand domain and trend analysis context

### 2. Announce Deep-Dive Phase

Inform the user about the analysis approach:

"Now we'll conduct a comprehensive deep-dive analysis of **[Selected Project Name]**.

This phase will cover:
1. **Competitive Analysis** - Detailed review of existing solutions and their limitations
2. **Feature Planning** - Complete feature set with MVP prioritization
3. **Architecture Exploration** - Technical stack and design considerations
4. **Market Positioning** - How to differentiate and capture attention
5. **Critical Validation** - Challenge assumptions and identify risks

This is where we validate that this idea is truly viable and worth building. I'll be thorough and critical to ensure we're not overlooking anything important.

Let's start with competitive analysis..."

### 3. Conduct Competitive Analysis

Perform detailed web research on existing solutions:

#### A. Research Existing Solutions
Search for:
- "[project concept] GitHub"
- "[problem space] open source tools"
- "[domain] popular libraries 2025"
- Similar projects mentioned in HackerNews, Reddit

For each competitor found, analyze:
- GitHub stars, forks, activity level
- Key features and capabilities
- User feedback and complaints (issues, discussions)
- Limitations and gaps
- Maintenance status and community health

#### B. Present Competitive Landscape

"I've researched the competitive landscape. Here's what exists:

**Competitor 1: [Name]**
- **Stars:** [count] | **Activity:** [Active/Stale]
- **Key Features:** [list]
- **Limitations:** [what they don't do well]
- **User Complaints:** [from issues/discussions]

**Competitor 2: [Name]**
[Same structure]

**Competitor 3: [Name]**
[Same structure]

**Gap Analysis:**
Based on this research, here's what's missing in the current landscape:
- [Gap 1]
- [Gap 2]
- [Gap 3]

Does this match your understanding of the competitive space? Are there any tools I missed?"

Wait for user validation and additions.

### 4. Define Feature Set

Collaborate on comprehensive feature planning:

"Based on the competitive gaps and user needs we've identified, let's define the feature set for [Project Name].

I'll propose features in three categories:
- **MVP (Must-Have)** - Essential for initial launch
- **V2 (Should-Have)** - Important but can come after MVP
- **Future (Nice-to-Have)** - Longer-term enhancements

Let me suggest an initial feature set..."

Present proposed features:

"**MVP Features (Must-Have for Launch):**
1. [Feature 1] - [Why essential]
2. [Feature 2] - [Why essential]
3. [Feature 3] - [Why essential]
[List 5-8 MVP features]

**V2 Features (Post-Launch Priority):**
1. [Feature 1] - [Value proposition]
2. [Feature 2] - [Value proposition]
[List 3-5 V2 features]

**Future Features (Long-term Vision):**
1. [Feature 1] - [Strategic value]
2. [Feature 2] - [Strategic value]
[List 2-4 future features]

What do you think? Should we adjust the prioritization or add/remove features?"

Engage in discussion and refine based on user input.

### 5. Explore Architecture Options

Discuss technical approach and stack:

"Let's explore the technical architecture for [Project Name].

**Technical Considerations:**
1. **Programming Language:** [Recommendation with rationale]
2. **Core Framework/Library:** [Recommendation with rationale]
3. **Key Dependencies:** [List with justifications]
4. **Architecture Pattern:** [e.g., CLI, library, service, etc.]

**Trade-offs to Consider:**
- [Trade-off 1: e.g., "Performance vs. Developer Experience"]
- [Trade-off 2: e.g., "Feature richness vs. Simplicity"]
- [Trade-off 3: e.g., "Batteries-included vs. Extensible"]

Would you like me to research specific libraries or frameworks using Context-7 to ensure we have accurate information about their capabilities and limitations?"

If user requests Context-7 research:
- Use Context-7 to look up specific libraries/frameworks
- Present findings about capabilities, limitations, community support
- Include in architecture discussion

### 6. Validate Market Positioning

Discuss go-to-market strategy:

"**Differentiation Strategy:**
How will [Project Name] stand out?
- [Differentiator 1 from competitive analysis]
- [Differentiator 2 from unique features]
- [Differentiator 3 from positioning]

**Target Audience:**
Who are we building for?
- [Primary audience segment]
- [Secondary audience segment]
- [Specific use cases]

**Value Proposition:**
Why will developers choose this over alternatives?
[Clear, compelling statement]

**Initial Launch Strategy:**
- [Launch channel 1: e.g., "Post on HackerNews"]
- [Launch channel 2: e.g., "Share in relevant subreddits"]
- [Launch channel 3: e.g., "Developer community forums"]

Does this positioning resonate with you?"

### 7. Apply Critical Validation

Prompt user to use Advanced Elicitation:

"Before we move to creating the final technical specification, I recommend using **Advanced Elicitation** to challenge our assumptions and find potential blind spots.

This will help us identify:
- Risks we haven't considered
- Alternative approaches we might have overlooked
- Questions that need deeper investigation
- Potential pitfalls in our plan

Would you like to run Advanced Elicitation now? (Select [A] from the menu)"

### 8. Document Deep-Dive Analysis

Prepare the Deep-Dive Analysis section:

```markdown
## Deep-Dive Analysis: [Project Name]

**Analysis Date:** [Current date]
**Selected Project:** [Project Name from step 5]

### Competitive Analysis

#### Existing Solutions

**[Competitor 1 Name]**
- **Repository:** [GitHub link]
- **Stars:** [count] | **Forks:** [count] | **Status:** [Active/Stale]
- **Key Features:**
  - [Feature 1]
  - [Feature 2]
  - [Feature 3]
- **Limitations:**
  - [Limitation 1]
  - [Limitation 2]
- **User Feedback:** [Summary of complaints/requests from issues]

[Repeat for all major competitors]

#### Gap Analysis

**Identified Gaps in Current Solutions:**
1. [Gap 1 with detailed explanation]
2. [Gap 2 with detailed explanation]
3. [Gap 3 with detailed explanation]

**Our Opportunity:**
[How this project will fill the gaps]

### Feature Planning

#### MVP Features (Must-Have)
1. **[Feature Name]**
   - **Description:** [What it does]
   - **User Value:** [Why it's essential]
   - **Complexity:** [Low/Medium/High]

[Repeat for all MVP features]

#### V2 Features (Post-Launch)
1. **[Feature Name]**
   - **Description:** [What it does]
   - **User Value:** [Why it's important]
   - **Dependency:** [What MVP features it builds on]

[Repeat for V2 features]

#### Future Features (Long-term)
[List with brief descriptions]

### Architecture Considerations

**Recommended Technology Stack:**
- **Language:** [Language] - [Rationale]
- **Core Framework:** [Framework] - [Rationale]
- **Key Dependencies:**
  - [Dependency 1] - [Purpose and justification]
  - [Dependency 2] - [Purpose and justification]
  - [Dependency 3] - [Purpose and justification]

**Architecture Pattern:** [Description of overall structure]

**Key Trade-offs:**
- [Trade-off 1 with decision]
- [Trade-off 2 with decision]
- [Trade-off 3 with decision]

**Context-7 Research Findings (if applicable):**
[Summary of library/framework research conducted]

### Market Positioning

**Primary Differentiation:**
[Clear statement of how this is different/better]

**Target Audience:**
- **Primary:** [Specific segment with characteristics]
- **Secondary:** [Additional segments]

**Value Proposition:**
[Compelling one-paragraph statement of why developers should use this]

**Launch Strategy:**
1. [Launch approach 1]
2. [Launch approach 2]
3. [Launch approach 3]

### Validation and Risk Assessment

**Key Assumptions:**
1. [Assumption 1]
2. [Assumption 2]
3. [Assumption 3]

**Identified Risks:**
1. [Risk 1 with mitigation approach]
2. [Risk 2 with mitigation approach]
3. [Risk 3 with mitigation approach]

**Success Factors:**
- [Critical factor 1]
- [Critical factor 2]
- [Critical factor 3]
```

### 9. Update Output Document

Write the Deep-Dive Analysis section to {outputFile}:
- Add the complete section after Ranking Analysis
- Update frontmatter: `lastStep: 'deep-dive'`
- Ensure `stepsCompleted` array now includes: `[1, 2, 3, 4, 5, 6]`

### 10. Present MENU OPTIONS

Display: "**Select an Option:** [A] Advanced Elicitation [P] Party Mode [C] Continue to Technical Specification"

#### Menu Handling Logic:
- IF A: Execute {advancedElicitationTask} with context: "Critically review the deep-dive analysis to identify assumptions, risks, gaps, or alternative approaches we should consider"
- IF P: Execute {partyModeWorkflow} with context: "Get diverse perspectives on the competitive positioning, feature prioritization, and architecture decisions"
- IF C: Save content to {outputFile}, update frontmatter, then only then load, read entire file, then execute {nextStepFile}
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#10-present-menu-options)

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- After other menu items execution completes, redisplay the menu
- User can chat or ask questions - always respond and then end with display again of the menu options
- STRONGLY ENCOURAGE using Advanced Elicitation before continuing

## CRITICAL STEP COMPLETION NOTE

Deep-dive analysis must be comprehensive and validated:
- Detailed competitive analysis with specific competitors researched
- Complete feature set defined with MVP/V2/Future prioritization
- Architecture considerations documented with trade-offs
- Market positioning and launch strategy defined
- Critical validation applied (preferably through Advanced Elicitation)
- Deep-Dive Analysis section written to {outputFile}
- Frontmatter updated with stepsCompleted: [1, 2, 3, 4, 5, 6]
- User has selected [C] to continue

ONLY WHEN [C continue option] is selected and deep-dive analysis is complete, will you then load and read fully `{nextStepFile}` to execute and begin technical specification synthesis.

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- Comprehensive competitive research with 3+ competitors analyzed
- Specific competitors include GitHub links, star counts, and detailed limitations
- Gap analysis clearly identifies opportunities
- Feature set defined with clear MVP/V2/Future categorization
- Each feature includes description, user value, and complexity/dependencies
- Architecture recommendations with justified technology choices
- Trade-offs explicitly discussed and resolved
- Market positioning with clear differentiation and value proposition
- Launch strategy defined
- Critical validation applied (Advanced Elicitation encouraged)
- Deep-Dive Analysis section written to output document
- User engaged in validation and refinement throughout

### ❌ SYSTEM FAILURE:
- Superficial competitive analysis without real web research
- Vague feature descriptions without prioritization
- Architecture recommendations without justification
- Not using Context-7 when technical accuracy is needed
- Skipping critical validation step
- Proceeding without user confirmation of analysis
- Not documenting trade-offs and decisions

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
