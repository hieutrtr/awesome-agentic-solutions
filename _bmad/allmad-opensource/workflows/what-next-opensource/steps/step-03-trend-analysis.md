---
name: 'step-03-trend-analysis'
description: 'Analyze current trends using web research and GitHub data'

<!-- Path Definitions -->
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/what-next-opensource'

# File References (all use {variable} format in file)
thisStepFile: '{workflow_path}/steps/step-03-trend-analysis.md'
nextStepFile: '{workflow_path}/steps/step-04-ideation.md'
workflowFile: '{workflow_path}/workflow.md'
outputFile: '{output_folder}/opensource-project-spec-{project_name}.md'

# Task References
advancedElicitationTask: '{project-root}/_bmad/core/tasks/advanced-elicitation.xml'
partyModeWorkflow: '{project-root}/_bmad/core/workflows/party-mode/workflow.md'

---

# Step 3: Trend Analysis

## STEP GOAL:
To conduct comprehensive research on current trends, pain points, and opportunities within the defined domain using web search, GitHub analysis, and community insights to inform project ideation.

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
- ✅ You bring research capabilities and trend analysis expertise, user brings domain knowledge and validation, and together we produce something better than we could on our own
- ✅ Maintain collaborative and analytical tone throughout

### Step-Specific Rules:
- 🎯 Focus only on research and trend analysis within the defined domain
- 🚫 FORBIDDEN to suggest specific project ideas yet (that comes in step 4)
- 💬 Approach: Systematic multi-source research with user validation
- 📋 Document all findings with sources for credibility

## EXECUTION PROTOCOLS:
- 🎯 Conduct thorough web research across multiple platforms
- 💾 Compile trend analysis summary with data sources
- 📖 Update output document with Trend Analysis section
- 🚫 FORBIDDEN to proceed until comprehensive research is complete

## CONTEXT BOUNDARIES:
- Available context: Domain definition from step 2 in {outputFile}
- Focus: Current trends, pain points, and opportunities in domain
- Limits: Analysis only - no project ideation yet
- Dependencies: Domain definition must be complete

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read Current State

Read the output document at {outputFile} to:
- Retrieve the domain definition from previous step
- Verify domain is clearly defined
- Review any domain context and target audience information

### 2. Announce Research Plan

Inform the user about the research approach:

"Now that we've defined your domain focus as **[domain]**, I'll conduct comprehensive trend analysis across multiple sources:

1. **GitHub Trending** - Popular and emerging repositories
2. **HackerNews** - Community discussions and pain points
3. **Reddit** (relevant subreddits) - Developer experiences and needs
4. **Stack Overflow** - Common technical challenges and questions
5. **Tech Blogs and News** - Industry trends and innovations

This will take a few minutes as I gather data from multiple sources. I'll share my findings with you for validation."

### 3. Conduct Multi-Source Research

Perform systematic web research:

#### A. GitHub Trending Analysis
Search for:
- "GitHub trending [domain]"
- "GitHub stars [domain] 2025"
- Top repositories in the domain (analyze star counts, fork patterns, activity)

Document:
- Most popular projects (with star counts)
- Emerging projects showing rapid growth
- Common patterns in successful projects
- Gaps or underserved areas

#### B. HackerNews Research
Search for:
- "[domain] site:news.ycombinator.com"
- Recent discussions about pain points in the domain
- Complaints about existing tools
- Feature requests and wishlist items

Document:
- Key discussion themes
- Pain points mentioned frequently
- Desired features or capabilities
- Community sentiment

#### C. Reddit Community Research
Search for:
- "[domain] subreddit discussions"
- "[domain] pain points reddit"
- Developer complaints and challenges

Document:
- User pain points and frustrations
- Workflow challenges
- Tool limitations
- Unmet needs

#### D. Stack Overflow Research
Search for:
- "Most viewed [domain] questions Stack Overflow"
- "[domain] common problems Stack Overflow"

Document:
- Frequently asked questions
- Recurring technical challenges
- Areas where developers struggle
- Missing documentation or tooling

#### E. Industry Trends
Search for:
- "[domain] trends 2025"
- "[domain] future predictions"
- "[domain] emerging technologies"

Document:
- Market direction and momentum
- Emerging technologies in the space
- Industry predictions
- Investment trends

### 4. Synthesize Research Findings

After completing research, synthesize findings into clear categories:

"I've completed my research across multiple sources. Here's what I found:

**GitHub Landscape:**
[Summary of popular projects, star patterns, gaps]

**Community Pain Points:**
[Summary of common complaints and challenges]

**Emerging Trends:**
[Summary of new directions and opportunities]

**Technical Challenges:**
[Summary of recurring problems and friction points]

Before I document these findings, do these align with your understanding of the [domain] space? Are there any insights you'd like me to explore further?"

Wait for user validation and feedback.

### 5. Document Trend Analysis

Prepare comprehensive Trend Analysis section:

```markdown
## Trend Analysis

**Analysis Date:** [Current date]
**Domain:** [domain from step 2]

### GitHub Landscape

**Popular Projects:**
| Repository | Stars | Key Features | Gap Analysis |
|------------|-------|--------------|--------------|
| [repo 1] | [stars] | [features] | [what's missing] |
| [repo 2] | [stars] | [features] | [what's missing] |
| [repo 3] | [stars] | [features] | [what's missing] |

**Emerging Trends:**
- [Trend 1 with supporting data]
- [Trend 2 with supporting data]
- [Trend 3 with supporting data]

### Community Pain Points

**From HackerNews:**
- [Pain point 1] - [source link]
- [Pain point 2] - [source link]
- [Pain point 3] - [source link]

**From Reddit:**
- [Pain point 1] - [source link]
- [Pain point 2] - [source link]
- [Pain point 3] - [source link]

### Technical Challenges

**Common Stack Overflow Issues:**
- [Challenge 1] - [frequency/views]
- [Challenge 2] - [frequency/views]
- [Challenge 3] - [frequency/views]

### Market Opportunities

**Identified Gaps:**
1. [Gap 1 with explanation]
2. [Gap 2 with explanation]
3. [Gap 3 with explanation]

**Success Patterns:**
- [Pattern 1 from successful projects]
- [Pattern 2 from successful projects]
- [Pattern 3 from successful projects]

### Key Insights for Project Ideation

[Synthesized insights that will guide ideation in next step]
```

### 6. Update Output Document

Write the Trend Analysis section to {outputFile}:
- Add the complete section after the Domain Definition
- Update frontmatter: `lastStep: 'trend-analysis'`
- Ensure `stepsCompleted` array now includes: `[1, 2, 3]`

### 7. Preview for User

Share a summary of the trend analysis with the user:

"I've documented comprehensive trend analysis covering:
- [X] popular GitHub repositories analyzed
- [X] community discussions reviewed
- [X] pain points identified
- [X] market opportunities discovered

The full analysis is now in your project specification document. We're ready to move into ideation where we'll use these insights to generate specific project ideas."

### 8. Present MENU OPTIONS

Display: "**Select an Option:** [A] Advanced Elicitation [P] Party Mode [C] Continue to Ideation"

#### Menu Handling Logic:
- IF A: Execute {advancedElicitationTask} with context: "Review the trend analysis for overlooked opportunities, alternative interpretations, or missing data sources"
- IF P: Execute {partyModeWorkflow} with context: "Get diverse perspectives on the trend analysis findings"
- IF C: Save content to {outputFile}, update frontmatter, then only then load, read entire file, then execute {nextStepFile}
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#8-present-menu-options)

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- After other menu items execution completes, redisplay the menu
- User can chat or ask questions - always respond and then end with display again of the menu options

## CRITICAL STEP COMPLETION NOTE

Trend analysis must be comprehensive and documented in {outputFile} with:
- Complete Trend Analysis section with multi-source research
- Data from GitHub, HackerNews, Reddit, Stack Overflow, and industry sources
- Clear insights documented with source links
- Frontmatter updated with stepsCompleted: [1, 2, 3]
- User has selected [C] to continue

ONLY WHEN [C continue option] is selected and trend analysis is documented, will you then load and read fully `{nextStepFile}` to execute and begin ideation.

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- Comprehensive research across 5+ data sources
- GitHub trending analysis with specific projects and star counts
- Community pain points documented with source links
- Technical challenges identified from Stack Overflow
- Market opportunities and gaps clearly identified
- Trend Analysis section written to output document
- User validated findings before documentation
- Frontmatter updated with step completion
- Ready to proceed to ideation

### ❌ SYSTEM FAILURE:
- Conducting superficial research from only 1-2 sources
- Making up data or trends without actual web search
- Suggesting specific project ideas (premature)
- Not providing source links for claims
- Proceeding without user validation of findings
- Not updating output document with complete analysis

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
