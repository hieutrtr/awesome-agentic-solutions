---
name: 'step-03-generate-reports'
description: 'Generate both overview and detailed analysis reports based on gathered findings'

# Path Definitions
workflow_path: '{project-root}/_bmad-output/bmb-creations/workflows/opensource-analyser'

# File References
thisStepFile: '{workflow_path}/steps/step-03-generate-reports.md'
workflowFile: '{workflow_path}/workflow.md'

# Tracking file and output files
trackingFile: 'opensources/{{project-name}}-report/.analysis-tracking.md'
overviewFile: 'opensources/{{project-name}}-report/overview.md'
detailedReportFile: 'opensources/{{project-name}}-report/detailed-report.md'

---

# Step 3: Generate Reports

## STEP GOAL:

To generate both output reports (overview.md and detailed-report.md) based on the analysis findings from step 2, validate the reports, and mark the workflow as complete.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER generate content without proper data
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: This is the final step - mark workflow complete when done
- 📋 YOU ARE A TECHNICAL WRITER AND ANALYST

### Role Reinforcement:

- ✅ You are an Opensource Project Analyst and Technical Documentation Writer
- ✅ If you already have been given communication or persona patterns, continue to use those while playing this new role
- ✅ You transform analysis data into clear, structured reports
- ✅ You bring expertise in technical writing, documentation structure, and clarity
- ✅ Maintain professional, informative, balanced, objective tone

### Step-Specific Rules:

- 🎯 Focus ONLY on report generation from existing data
- 🚫 FORBIDDEN to perform new analysis (all data from step 2)
- 💬 Generate well-structured, readable markdown reports
- ✅ Validate both reports before marking complete

## EXECUTION PROTOCOLS:

- 🎯 Generate both reports following approved templates
- 💾 Save reports to correct locations
- 📖 Update frontmatter `stepsCompleted: [1, 2, 3]`, `completed: true`
- 🚫 FORBIDDEN to skip validation or completion marking

## CONTEXT BOUNDARIES:

- All analysis findings available in tracking file
- Report templates defined in workflow plan
- This is the final step - produces deliverables
- No menu after this step - workflow completes

## REPORT GENERATION SEQUENCE:

### 1. Load Analysis Findings

Read tracking file to retrieve all analysis data:
- Project metadata (version, license, activity)
- Technology stack (languages, frameworks, tools)
- Architecture analysis (patterns, structure)
- Use cases (primary use cases, target users)
- Evaluation (strengths, weaknesses, performance)
- Alternatives (competing projects with comparisons)
- Code quality observations
- Community and maintenance insights

Display:
"**Generating Reports: {projectName}**

Creating:
1. overview.md - Quick summary for decision-makers
2. detailed-report.md - Comprehensive technical analysis

Proceeding..."

### 2. Generate overview.md (Short Overview)

Create `opensources/{project-name}-report/overview.md` following this structure:

```markdown
# {Project Name} - Overview

## Executive Summary

[Write 2-3 paragraph summary covering:
- What the project is and its primary purpose
- Key technology stack highlights
- Main use cases
- Overall assessment with balanced perspective]

## Technology Stack

- **Primary Language**: [Language]
- **Key Technologies**: [Frameworks, libraries]
- **Framework/Platform**: [Main framework if applicable]
- **Build Tools**: [Build system]
- **Testing**: [Test frameworks]

## Primary Use Cases

1. **[Use Case 1]**: [Brief description]
2. **[Use Case 2]**: [Brief description]
3. **[Use Case 3]**: [Brief description]

## Key Pros & Cons

**Pros:**
- [Strength 1 with brief explanation]
- [Strength 2 with brief explanation]
- [Strength 3 with brief explanation]

**Cons:**
- [Limitation 1 with brief explanation]
- [Limitation 2 with brief explanation]
- [Limitation 3 with brief explanation]

## Main Alternatives

- **[Alternative 1]**: [Brief description and when to choose it]
- **[Alternative 2]**: [Brief description and when to choose it]
- **[Alternative 3]**: [Brief description and when to choose it]

---

*Analysis generated: {current-date}*
*Source: {projectUrl}*
```

Progress Update: "overview.md generated."

### 3. Generate detailed-report.md (Comprehensive Analysis)

Create `opensources/{project-name}-report/detailed-report.md` following this structure:

```markdown
# {Project Name} - Detailed Analysis Report

## Project Overview

### Description

[Comprehensive project description including:
- What problem it solves
- How it works
- Key features and capabilities
- Target audience and use cases]

### Project Information

- **Repository**: {projectUrl}
- **Official Website**: [URL if different from repo]
- **License**: [License type]
- **Current Version**: [Version]
- **Last Updated**: [Date]
- **Contributors**: [Number]
- **Stars**: [GitHub stars if applicable]
- **Primary Language**: [Language]

## Technology Stack Analysis

### Core Technologies

[Detailed breakdown of:
- Programming languages and why they're used
- Key frameworks and their roles
- Major libraries and dependencies
- Build and package management tools
- Development and testing tools]

### Architecture Patterns

[Analysis of:
- Overall architectural approach (monolith, microservices, etc.)
- Design patterns employed
- Code organization principles
- Module/component structure
- API design philosophy
- Data flow patterns]

### Dependencies

[Key dependencies listed with:
- Purpose of each major dependency
- Version constraints
- Any notable dependency considerations]

## Use Cases

### Primary Use Cases

[Detailed descriptions with examples for each main use case]

**Use Case 1: [Name]**
- Description: [Detailed explanation]
- Example: [Concrete example]
- Benefits: [Why use this project for this case]

[Repeat for each primary use case]

### Common Applications

[Real-world usage scenarios:
- Industry applications
- Common integration patterns
- Typical deployment contexts]

### Target Users

[Who benefits from this project:
- Developer personas
- Organization types
- Skill level requirements]

## Pros and Cons Analysis

### Strengths

[Detailed analysis of advantages:]

**Technical Advantages:**
- [Advantage 1 with detailed explanation]
- [Advantage 2 with detailed explanation]

**Developer Experience:**
- [DX benefit 1]
- [DX benefit 2]

**Community and Ecosystem:**
- [Community strength 1]
- [Ecosystem strength 2]

### Weaknesses

[Detailed analysis of limitations:]

**Technical Limitations:**
- [Limitation 1 with explanation]
- [Limitation 2 with explanation]

**Challenges:**
- [Challenge 1 such as learning curve]
- [Challenge 2 such as missing features]

**Ecosystem Gaps:**
- [Gap 1]
- [Gap 2]

### Performance Characteristics

[Performance insights:]
- Scalability: [How it scales]
- Resource Requirements: [CPU, memory, etc.]
- Known Bottlenecks: [Performance considerations]
- Benchmarks: [If available]

## Alternative Solutions

### Alternative 1: [Name]

- **Description**: [What it is]
- **Similarities**: [How it's similar to analyzed project]
- **Differences**: [Key differences]
- **When to Choose**: [Scenarios where this alternative is better]
- **Relative Popularity**: [Comparison of adoption]

[Repeat for each alternative - typically 3-5 alternatives]

## Code Quality Observations

### Code Organization

[Analysis of:
- Project structure clarity
- Modularity and separation of concerns
- Naming conventions
- Code readability]

### Documentation Quality

[Assessment of:
- README completeness
- API documentation availability
- Code comments quality
- Examples and tutorials
- Getting started guides]

### Test Coverage

[Testing practices observed:
- Test framework used
- Test coverage (if measurable)
- Testing approach (unit, integration, e2e)
- CI/CD integration]

## Community and Maintenance

### Community Activity

- **GitHub Stars**: [Number]
- **Forks**: [Number]
- **Contributors**: [Number]
- **Open Issues**: [Number]
- **Closed Issues**: [Number]
- **Pull Requests**: [Activity level]
- **Discussion**: [Forum/chat activity]

### Maintenance Status

- **Last Commit**: [Date]
- **Release Frequency**: [How often releases happen]
- **Issue Response Time**: [How quickly issues are addressed]
- **Active Maintainers**: [Number and activity level]
- **Project Maturity**: [Assessment of stability]

### Ecosystem

- **Plugins/Extensions**: [Availability]
- **Related Projects**: [Notable integrations]
- **Known Adopters**: [Organizations using it]
- **Learning Resources**: [Tutorials, courses, books]

## Conclusion

[Summary of findings and recommendations:]

**Overall Assessment:**
[Balanced summary of the project's value proposition]

**Best Suited For:**
[Specific scenarios where this project excels]

**Considerations:**
[Important factors to consider before adopting]

**Recommendation:**
[Final recommendation with nuance]

---

*Detailed analysis generated: {current-date}*
*Analysis workflow: Opensource Codebase Analyser v1.0*
*Source: {projectUrl}*
*Codebase Reference: {codebaseRef}*
```

Progress Update: "detailed-report.md generated."

### 4. Validation

Verify both reports:

**Validation Checklist:**
- ✅ Both files created successfully in correct location
- ✅ overview.md has all required sections
- ✅ detailed-report.md has all required sections
- ✅ All sections populated with data (no empty sections)
- ✅ Markdown formatting is correct
- ✅ Links and references are valid
- ✅ Balanced perspective (not biased)

If any validation issues found, fix them before proceeding.

### 5. Update Tracking File

Update frontmatter in tracking file:
```yaml
stepsCompleted: [1, 2, 3]
completed: true
lastStep: "Report Generation"
analysisCompleted: "{date from step 2}"
reportsGenerated: "{current-date}"
```

Append completion note to tracking file:
```markdown
## Workflow Complete

- [x] Step 1: Initialization
- [x] Step 2: Codebase Analysis
- [x] Step 3: Report Generation

**Reports Generated:**
- `overview.md` - Quick summary
- `detailed-report.md` - Comprehensive analysis

**Completion Date**: {current-date}
```

### 6. Present Success Message

Display completion message:

"**🎉 Analysis Complete!**

Reports successfully generated for **{projectName}**:

📄 **overview.md**
   Quick summary with key insights
   Location: `opensources/{project-name}-report/overview.md`

📊 **detailed-report.md**
   Comprehensive technical analysis
   Location: `opensources/{project-name}-report/detailed-report.md`

**Analysis Summary:**
- Technology Stack: Documented
- Architecture: Analyzed
- Use Cases: Identified
- Pros & Cons: Evaluated
- Alternatives: Researched

You can now review these reports and use them for:
- Technical decision-making
- Project evaluation
- Team presentations
- Documentation reference

To analyze another project, run this workflow again with different project information.

**Workflow Status**: ✅ Complete"

### 7. Completion (No Menu)

This step has no menu - workflow ends here.

Workflow is complete when:
- Both reports generated and validated
- Tracking file marked complete
- User notified of success

---

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- overview.md generated with all required sections
- detailed-report.md generated with all required sections
- Both reports validated successfully
- All sections populated with analysis data
- Reports are well-structured and readable
- Frontmatter updated: stepsCompleted: [1, 2, 3], completed: true
- User presented with success message and file locations
- Workflow marked complete

### ❌ SYSTEM FAILURE:

- Generating reports without analysis data
- Missing required sections in either report
- Empty or incomplete sections
- Poor formatting or structure
- Not validating reports before completion
- Not updating tracking file frontmatter
- Not marking workflow complete

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.

## CRITICAL STEP COMPLETION NOTE

This is the FINAL step. When both reports are generated, validated, and tracking file is updated with completion status, the workflow ends successfully. There is no next step to load.
