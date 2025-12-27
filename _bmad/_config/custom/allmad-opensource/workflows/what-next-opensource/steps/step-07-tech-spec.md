---
name: 'step-07-tech-spec'
description: 'Generate comprehensive technical specification document'

<!-- Path Definitions -->
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/what-next-opensource'

# File References (all use {variable} format in file)
thisStepFile: '{workflow_path}/steps/step-07-tech-spec.md'
workflowFile: '{workflow_path}/workflow.md'
outputFile: '{output_folder}/opensource-project-spec-{project_name}.md'

# Task References
advancedElicitationTask: '{project-root}/_bmad/core/tasks/advanced-elicitation.xml'

---

# Step 7: Technical Specification

## STEP GOAL:
To synthesize all research, analysis, and planning into a comprehensive technical specification document that is immediately actionable for project implementation.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:
- 🛑 NEVER generate content without user input
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: This is the FINAL step - mark workflow as complete
- 📋 YOU ARE A FACILITATOR, not a content generator

### Role Reinforcement:
- ✅ You are a Strategic Open Source Advisor & Trend Analyst
- ✅ If you already have been given a name, communication_style and identity, continue to use those while playing this new role
- ✅ We engage in collaborative dialogue, not command-response
- ✅ You bring synthesis and technical documentation expertise, user brings final validation and approval, and together we produce something better than we could on our own
- ✅ Maintain collaborative and professional tone throughout

### Step-Specific Rules:
- 🎯 Focus on synthesizing all previous work into complete technical spec
- 🚫 FORBIDDEN to add new research or change direction
- 💬 Approach: Comprehensive documentation of validated plan
- 📋 This is the final deliverable - ensure completeness and quality

## EXECUTION PROTOCOLS:
- 🎯 Synthesize all sections from previous steps
- 💾 Complete all required specification sections
- 📖 Use Context-7 for technical accuracy if needed
- 🚫 FORBIDDEN to leave any required section incomplete
- ✅ Mark workflow as complete in frontmatter

## CONTEXT BOUNDARIES:
- Available context: Complete workflow from steps 1-6 in {outputFile}
- Focus: Synthesis and final specification completion
- Limits: No new research - synthesize existing work
- Dependencies: All previous steps must be complete

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read Complete Current State

Read the output document at {outputFile} to review:
- Domain Definition (step 2)
- Trend Analysis (step 3)
- Project Ideas Candidates (step 4)
- Ranking Analysis (step 5)
- Deep-Dive Analysis (step 6)
- Selected project name from frontmatter

### 2. Announce Final Phase

Inform the user:

"We've reached the final step! Now I'll synthesize all our research and planning into a comprehensive technical specification for **[Project Name]**.

This specification will include:
1. **Project Overview and Value Proposition** - Executive summary
2. **Target Users and Use Cases** - Who benefits and how
3. **Core Features and Functionality** - Complete feature specifications
4. **Technical Architecture and Stack** - Implementation blueprint
5. **Implementation Roadmap** - Phased development plan
6. **Competitive Analysis** - Market positioning summary
7. **Success Metrics** - How to measure impact and adoption

I'll draft each section based on all our previous work. You'll have a chance to review and refine before we finalize."

### 3. Synthesize Project Overview

Create the executive summary:

"**Draft: Project Overview and Value Proposition**

**Project Name:** [Name]

**One-Line Description:**
[Compelling elevator pitch]

**Problem Statement:**
[Clear articulation of the problem, referencing trend analysis findings]

**Solution Description:**
[How this project solves the problem, key approach]

**Key Value Propositions:**
- [Value prop 1 from competitive differentiation]
- [Value prop 2 from unique features]
- [Value prop 3 from market positioning]

**Differentiation from Existing Solutions:**
[Clear statement of competitive advantages based on gap analysis]

Does this accurately capture the project essence?"

Wait for user feedback and refine.

### 4. Define Target Users and Use Cases

Document the audience:

"**Draft: Target Users and Use Cases**

**Primary User Personas:**

**Persona 1: [Name/Title]**
- **Characteristics:** [Description from domain definition and deep-dive]
- **Pain Points:** [Specific problems they face]
- **How This Helps:** [Value delivered]

**Persona 2: [Name/Title]**
[Same structure]

**Key Use Cases:**

**Use Case 1: [Scenario Name]**
- **Context:** [When/why this happens]
- **Current Approach:** [How they do it now]
- **With [Project Name]:** [How our project improves it]
- **Outcome:** [Benefit achieved]

[Repeat for 3-5 key use cases]

**User Pain Points Addressed:**
1. [Pain point 1 from trend analysis] → [How we solve it]
2. [Pain point 2 from trend analysis] → [How we solve it]
3. [Pain point 3 from trend analysis] → [How we solve it]

Does this comprehensively cover the target audience?"

Wait for validation.

### 5. Document Core Features

Detail the feature specifications:

"**Draft: Core Features and Functionality**

**MVP Features (Phase 1 - Must-Have):**

**Feature 1: [Name]**
- **Description:** [Detailed functionality]
- **User Value:** [Why it matters]
- **Technical Approach:** [How to implement]
- **Acceptance Criteria:**
  - [Criterion 1]
  - [Criterion 2]
  - [Criterion 3]
- **Estimated Complexity:** [Low/Medium/High]

[Repeat for all MVP features from deep-dive]

**V2 Features (Phase 2 - Post-Launch):**
[Same structure for V2 features]

**Future Features (Phase 3+ - Long-term Vision):**
[Brief descriptions of future features]

**Feature Prioritization Rationale:**
[Explain why MVP was chosen based on user needs and feasibility]

Is the feature set complete and well-specified?"

Wait for validation.

### 6. Specify Technical Architecture

Document the technical blueprint:

"**Draft: Technical Architecture and Stack Recommendations**

**Recommended Technology Stack:**

**Core Technologies:**
- **Language:** [Language] - [Detailed rationale from deep-dive]
- **Framework:** [Framework] - [Why this choice]
- **Runtime/Platform:** [If applicable]

**Key Dependencies:**
| Dependency | Purpose | Rationale |
|------------|---------|-----------|
| [Lib 1] | [What it does] | [Why we need it] |
| [Lib 2] | [What it does] | [Why we need it] |
| [Lib 3] | [What it does] | [Why we need it] |

**Architecture Pattern:**
[Description of overall system design - CLI, library, service, plugin, etc.]

**System Design Overview:**
[High-level architecture diagram description or component breakdown]

**Key Design Decisions:**
1. **[Decision 1]:** [Choice made] - [Rationale from trade-offs]
2. **[Decision 2]:** [Choice made] - [Rationale from trade-offs]
3. **[Decision 3]:** [Choice made] - [Rationale from trade-offs]

**Integration Points:**
[How this project integrates with other tools/systems]

**Quality and Maintainability:**
- **Testing Strategy:** [Approach to testing]
- **Documentation Plan:** [How to document the project]
- **Contribution Guidelines:** [How others can contribute]

If you'd like me to verify any technical details using Context-7, let me know."

If user requests Context-7 research, conduct it now.

Wait for validation.

### 7. Create Implementation Roadmap

Define the development phases:

"**Draft: Implementation Roadmap**

**Phase 1: MVP Development (Estimated: [X weeks/months])**

**Milestone 1.1: Core Infrastructure**
- [Task 1]
- [Task 2]
- [Task 3]
- **Deliverable:** [What's complete]

**Milestone 1.2: Essential Features**
- [Feature 1 implementation]
- [Feature 2 implementation]
- [Feature 3 implementation]
- **Deliverable:** [What's complete]

**Milestone 1.3: Polish and Launch Prep**
- [Task 1: Testing, docs, etc.]
- [Task 2: Launch materials]
- [Task 3: Community setup]
- **Deliverable:** [Ready for launch]

**Phase 2: Post-Launch Iteration (Estimated: [X months])**
- [V2 feature 1]
- [V2 feature 2]
- Community feedback integration
- **Deliverable:** [Mature stable version]

**Phase 3: Long-term Vision (Estimated: [X months+])**
- [Future feature 1]
- [Future feature 2]
- [Ecosystem expansion]

**Resource Requirements:**
- **Time Commitment:** [Based on user's availability from step 2]
- **Skills Needed:** [Technical skills required]
- **Key Challenges:** [Anticipated difficulties from deep-dive risks]

Does this roadmap feel realistic and achievable?"

Wait for validation.

### 8. Summarize Competitive Analysis

Consolidate the market positioning:

"**Draft: Competitive Analysis**

**Existing Solutions Comparison:**

| Solution | Stars | Strengths | Weaknesses | Our Advantage |
|----------|-------|-----------|------------|---------------|
| [Competitor 1] | [count] | [What they do well] | [Limitations] | [How we're better] |
| [Competitor 2] | [count] | [What they do well] | [Limitations] | [How we're better] |
| [Competitor 3] | [count] | [What they do well] | [Limitations] | [How we're better] |

**Market Positioning:**
[Statement of where this project fits in the ecosystem]

**Competitive Advantages:**
1. [Advantage 1 from gap analysis]
2. [Advantage 2 from differentiation]
3. [Advantage 3 from unique features]

**Gap Analysis Summary:**
[Key gaps in market that this project fills]

**Launch and Growth Strategy:**
1. [Initial launch approach from deep-dive]
2. [Community building tactics]
3. [Content and awareness strategies]
4. [Partnership opportunities]

Is the competitive positioning clear and compelling?"

Wait for validation.

### 9. Define Success Metrics

Establish measurable goals:

"**Draft: Success Metrics**

**GitHub Star Potential:**
- **Target (6 months):** [Number] stars - [Rationale based on similar projects]
- **Target (1 year):** [Number] stars
- **Target (2 years):** [Number] stars

**Adoption Metrics:**
- **Downloads/Installs:** [Target numbers]
- **Active Users:** [How to measure]
- **Contributor Growth:** [Community health indicators]

**Community Engagement Measures:**
- **Issue Response Time:** [Target SLA]
- **PR Review Time:** [Target SLA]
- **Community Discussions:** [Activity level indicators]
- **Documentation Usage:** [Views, searches, feedback]

**Quality Indicators:**
- **Test Coverage:** [Target percentage]
- **Bug Report Volume:** [Acceptable range]
- **Performance Benchmarks:** [Specific metrics if applicable]
- **User Satisfaction:** [How to measure - surveys, sentiment analysis]

**Milestone Indicators:**
- **Week 1:** [Early signal - e.g., "HackerNews front page"]
- **Month 1:** [First month target]
- **Month 3:** [Quarter target]
- **Month 6:** [Half-year target]
- **Year 1:** [Annual target]

**Leading Indicators of Success:**
- [Indicator 1 that suggests project is gaining traction]
- [Indicator 2 that suggests community is healthy]
- [Indicator 3 that suggests long-term viability]

Are these metrics realistic and measurable?"

Wait for validation.

### 10. Compile Final Technical Specification

Prepare the complete final specification:

```markdown
---
stepsCompleted: [1, 2, 3, 4, 5, 6, 7]
lastStep: 'technical-specification'
workflowComplete: true
domain: [domain]
selectedIdea: [project name]
date: [original start date]
completedDate: [current date]
user_name: {user_name}
---

# Open Source Project Technical Specification

# [Project Name]

**Created:** [Date]
**Last Updated:** [Date]
**Status:** Ready for Implementation

---

## Project Overview and Value Proposition

[Complete synthesized content from step 3]

---

## Target Users and Use Cases

[Complete content from step 4]

---

## Core Features and Functionality

[Complete content from step 5]

---

## Technical Architecture and Stack Recommendations

[Complete content from step 6]

---

## Implementation Roadmap

[Complete content from step 7]

---

## Competitive Analysis

[Complete content from step 8]

---

## Success Metrics

[Complete content from step 9]

---

## Appendix: Research Summary

### Domain Definition
[Summary from step 2]

### Trend Analysis Highlights
[Key findings from step 3]

### Ideation Process
[Summary of ideas considered from step 4]

### Evaluation and Selection
[Summary of ranking from step 5]

### Deep-Dive Findings
[Key insights from step 6]

---

**End of Technical Specification**

*This specification was created using the BMAD Open Source Project Discovery Workflow*
*All research, analysis, and recommendations are based on data collected on [date]*
```

### 11. Update Output Document

Finalize the output document at {outputFile}:
- Ensure all 7 required sections are complete and well-formatted
- Add Appendix with research summary
- Update frontmatter:
  - `stepsCompleted: [1, 2, 3, 4, 5, 6, 7]`
  - `lastStep: 'technical-specification'`
  - `workflowComplete: true`
  - `completedDate: [current date]`
- Verify document is ready for implementation

### 12. Present Final Document

Show the user the complete specification:

"**Your Open Source Project Technical Specification is Complete!**

I've synthesized all our research and planning into a comprehensive specification for **[Project Name]**.

**Document Summary:**
- **Project Overview:** ✅ Complete
- **Target Users & Use Cases:** ✅ Complete
- **Core Features:** ✅ Complete (MVP, V2, Future)
- **Technical Architecture:** ✅ Complete
- **Implementation Roadmap:** ✅ Complete
- **Competitive Analysis:** ✅ Complete
- **Success Metrics:** ✅ Complete

**What's Included:**
- Research-backed competitive analysis
- Validated feature prioritization
- Detailed technical architecture recommendations
- Phased implementation roadmap
- Measurable success criteria
- Complete market positioning

**Your specification is saved at:**
`{output_folder}/opensource-project-spec-{project_name}.md`

This document is ready to guide your implementation. You can:
- Start building immediately following the roadmap
- Share with collaborators or co-founders
- Use as basis for funding applications
- Reference during development to stay on track

Before I mark this workflow complete, would you like to review anything or make final adjustments?"

### 13. Final Validation

Engage in final discussion:
- Answer any questions
- Make any final refinements requested
- Confirm user satisfaction with the specification
- Ensure user feels confident to proceed with implementation

### 14. Present FINAL MENU OPTIONS

Display: "**Select an Option:** [A] Advanced Elicitation [C] Complete Workflow"

#### Menu Handling Logic:
- IF A: Execute {advancedElicitationTask} with context: "Final quality review of the complete technical specification - identify any gaps, inconsistencies, or areas needing clarification"
- IF C:
  1. Ensure all sections are complete in {outputFile}
  2. Update frontmatter: `workflowComplete: true`, `completedDate: [current date]`
  3. Present completion message
  4. DO NOT load any next step - workflow is complete
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#14-present-final-menu-options)

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY mark workflow complete when user selects 'C'
- After Advanced Elicitation, redisplay the menu
- User can request modifications - make them and redisplay menu

### 15. Completion Message

When user selects [C], present final message:

"**Workflow Complete! 🎉**

Your open source project technical specification for **[Project Name]** is ready!

**What We Accomplished:**
1. ✅ Defined your domain and target audience
2. ✅ Analyzed current trends across multiple sources
3. ✅ Generated and evaluated [X] project ideas
4. ✅ Ranked opportunities systematically
5. ✅ Conducted deep-dive competitive analysis
6. ✅ Created comprehensive technical specification

**Next Steps:**
1. Review the complete specification document
2. Set up your GitHub repository
3. Begin Phase 1 (MVP) development following the roadmap
4. Engage with target communities as you build
5. Plan your launch strategy

**Your Specification Location:**
`{output_folder}/opensource-project-spec-{project_name}.md`

Good luck with **[Project Name]**! I'm confident this research-backed plan will help you create a successful open source project. 🚀

*You can return to this workflow anytime to create specifications for additional project ideas.*"

## CRITICAL STEP COMPLETION NOTE

This is the FINAL step. Requirements for completion:
- All 7 required specification sections complete and high-quality
- Content synthesized from all previous steps (no new research)
- Appendix with research summary included
- Document saved to {outputFile}
- Frontmatter updated: `workflowComplete: true`, `stepsCompleted: [1,2,3,4,5,6,7]`, `completedDate`
- User satisfied with final specification
- User selected [C] Complete Workflow

ONLY WHEN [C] is selected will the workflow be marked complete. There is NO next step.

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- All 7 required sections present and complete
- Content synthesized from previous steps (not newly generated)
- Technical specifications are detailed and actionable
- Roadmap is realistic and phased appropriately
- Success metrics are measurable and grounded in research
- Document is professionally formatted and ready to use
- User validated all sections during creation
- Frontmatter correctly marked: `workflowComplete: true`
- Completion message presented
- User feels confident to begin implementation

### ❌ SYSTEM FAILURE:
- Any required section missing or incomplete
- Adding new research instead of synthesizing existing work
- Vague or generic content not grounded in workflow research
- Proceeding without user validation of each section
- Not marking workflow as complete in frontmatter
- Leaving user confused about next steps
- Document not actionable for implementation

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.

---

**This is the FINAL STEP of the workflow. Upon completion, the user will have a comprehensive, research-backed technical specification ready for implementation.**
