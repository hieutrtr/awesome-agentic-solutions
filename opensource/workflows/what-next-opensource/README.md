# What Next Open Source - Workflow

Strategic open source planning workflow that helps developers identify high-potential open source project opportunities through interactive brainstorming and trend analysis.

## Overview

This workflow helps you discover and validate open source project ideas by:
- Analyzing current trends in your domain of interest
- Generating data-driven project ideas
- Evaluating and ranking opportunities
- Creating comprehensive technical specifications

## Prerequisites

### Required
- Internet access for web research
- GitHub trends and community data access

### Optional (Enhances Experience)
- **Context-7 MCP Server**: Provides access to library/framework documentation for accurate technical recommendations
  - Installation: See [Context-7 Documentation](https://github.com/modelcontextprotocol/servers/tree/main/src/context-7)
  - Installation time: ~5-10 minutes
  - Highly recommended for Steps 06 and 07

## Installation

### For BMB Module (Standalone)

This workflow is already created in:
```
_bmad-output/bmb-creations/workflows/what-next-opensource/
```

To use it, invoke the workflow:
```bash
/what-next-opensource
```

### Optional: Install Context-7

For enhanced technical recommendations, install Context-7 MCP server:

1. Follow installation instructions at: https://github.com/modelcontextprotocol/servers/tree/main/src/context-7
2. Configure MCP server connection
3. Restart Claude Code
4. Workflow will automatically detect and use Context-7 when available

## Usage

### Starting the Workflow

Invoke the workflow:
```
/what-next-opensource
```

The workflow will:
1. Check for existing in-progress workflows
2. Initialize a new session or resume previous work
3. Guide you through 7 steps to create your technical specification

### Workflow Steps

1. **Initialization** - Setup and continuation detection
2. **Domain Definition** - Define your topic/domain of interest
3. **Trend Analysis** - Research current trends using web data
4. **Ideation** - Generate multiple project ideas (iterative)
5. **Ranking** - Compare and rank opportunities
6. **Deep-Dive** - Detailed analysis of selected idea(s)
7. **Technical Specification** - Generate comprehensive tech spec

### Session Continuity

The workflow supports pause/resume:
- Work can be completed across multiple sessions
- Progress is tracked automatically
- Resume where you left off anytime
- History tracked via sidecar file (avoids redundant research)

### Tips for Best Results

**Domain Definition (Step 2):**
- Be specific about your domain (e.g., "developer productivity tools" vs "productivity")
- Consider using Brainstorming option for domain exploration
- Provide optional context (your expertise, target audience) for better recommendations

**Trend Analysis (Step 3):**
- Review multiple data sources (GitHub, HackerNews, Reddit, Stack Overflow)
- Look for convergent signals across communities
- Note both what's trending and what pain points exist

**Ideation (Step 4):**
- Generate at least 3-5 ideas before proceeding
- Use [G] option to generate more ideas if first batch isn't satisfactory
- Party-Mode can provide diverse creative perspectives
- Don't rush - this is the creative exploration phase

**Ranking (Step 5):**
- Evaluate against multiple criteria (star potential, feasibility, differentiation, demand)
- Be honest about your capabilities and resources
- Select 1-2 ideas for deep-dive (focus is better than spreading thin)

**Deep-Dive (Step 6):**
- Advanced Elicitation helps validate assumptions
- Context-7 provides accurate library/framework information
- Thorough competitive analysis prevents duplicating existing solutions

**Technical Specification (Step 7):**
- Final output should be immediately actionable
- All 7 sections must be complete and detailed
- Use as blueprint for actual development

## Output

### Primary Output

Technical Specification Document saved to `_bmad-output/`:
- `opensource-project-spec-{project_name}.md`

### Document Sections

1. **Project Overview and Value Proposition**
2. **Target Users and Use Cases**
3. **Core Features and Functionality**
4. **Technical Architecture and Stack Recommendations**
5. **Implementation Roadmap**
6. **Competitive Analysis**
7. **Success Metrics** (GitHub star potential, adoption indicators)

### Intermediate Outputs

- Trend analysis summary
- Project idea candidates table
- Comparison matrix with rankings

## Features

### Research-Driven

- Web browsing for real-time trend data
- Multi-source validation (GitHub, HackerNews, Reddit, Stack Overflow)
- Data-backed recommendations

### Iterative Ideation

- Generate ideas in batches
- Loop back for more ideas if needed
- Prevents premature convergence

### Collaborative Tools

- **Brainstorming**: Domain exploration and idea generation
- **Party-Mode**: Multi-persona creative ideation
- **Advanced Elicitation**: Critical validation and deep questioning
- **Context-7**: Technical documentation access

### Memory and Learning

- Sidecar file tracks explored domains
- Records dismissed ideas with reasons
- Prevents redundant research across sessions

## Workflow Architecture

- **Pattern**: Iterative brainstorming with trend analysis
- **Type**: Hybrid (interactive + document generation)
- **Duration**: 2-4 sessions (research-intensive)
- **Collaboration Level**: High

## Troubleshooting

### Web Browsing Not Working

If web research fails:
- Check internet connection
- Workflow will prompt for manual input as fallback
- Can continue with reduced data quality

### Context-7 Not Available

Workflow continues without Context-7:
- Falls back to general knowledge
- Technical recommendations may be less current
- Consider installing for better results

### Workflow Not Resuming

If continuation doesn't work:
- Check output file exists at `_bmad-output/opensource-project-spec-{project_name}.md`
- Verify frontmatter has `stepsCompleted` array
- Start fresh workflow if corrupted

### No Good Ideas Generated

If ideation step produces poor results:
- Use [G] option to generate more ideas
- Refine domain definition (may be too broad/narrow)
- Try Party-Mode for diverse perspectives
- Consider different domain angle

## Support

For issues or questions:
- Check workflow plan: `workflow-plan-what-next-opensource.md`
- Review step files in `steps/` folder for detailed instructions
- Consult BMAD documentation

## Version

- **Created**: 2025-12-24
- **Module**: BMB (standalone)
- **Architecture**: Step-file based with continuation support

## License

Part of the BMAD Method toolkit.