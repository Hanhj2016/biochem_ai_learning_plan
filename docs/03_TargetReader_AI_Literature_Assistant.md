# TargetReader AI: Drug Target Literature Assistant

## Project Summary

**TargetReader AI** is an AI-assisted literature reading tool for Biochemistry students.

It helps summarize drug target abstracts or paper sections into a structured format that is easier for an undergraduate student to understand.

## Project Positioning

> A small AI reading assistant that helps students understand drug target papers faster, while reminding them to verify important claims manually.

---

# Why This Project Matters

Biochemistry students often struggle with scientific papers because:

- abstracts are dense
- methods are difficult
- drug targets may be unfamiliar
- assay descriptions are technical
- limitations may not be obvious
- AI summaries may sound confident but still be wrong

This project teaches the student to use AI responsibly for scientific reading.

---

# Key Use Cases

## Use Case 1: Structured Abstract Summary

### Input

Paper title and abstract.

### Output

- research question
- drug target
- biological system
- methods
- key findings
- limitations
- terms to learn
- what to verify manually

## Use Case 2: Drug Target Reading Guide

### Input

A drug target name, such as EGFR, HER2, or beta-lactamase.

### Output

- what the target is
- why it matters
- common assays
- common inhibitors or drug classes
- what to look for in papers

## Use Case 3: Paper Q&A

### Input

A paragraph or abstract.

### Output

The student can ask follow-up questions, such as:

- What is the main method?
- What does dose-dependent mean?
- What should I verify?
- What terms should I learn?

---

# Test Data Source

## First Version: Generated Abstract

Use generated fake abstracts first.

Reason:

- avoids copyright issues
- avoids PDF parsing complexity
- easier to control
- good for demo
- no dependence on external files

## Synthetic Abstract Generation Prompt

```text
Generate a realistic but fictional scientific abstract for a beginner biochemistry AI-reading project.

Topic:
A small-molecule inhibitor reduces EGFR signaling in cancer cells.

The abstract should:
1. be 150 to 220 words
2. mention a drug target
3. mention a cell-based assay
4. mention dose-dependent response
5. mention one limitation
6. not refer to a real paper
7. be clearly fictional

Return:
Title:
Abstract:
```

## Example Generated Abstract

```text
Title:
A small-molecule inhibitor reduces EGFR signaling in cancer cells

Abstract:
This fictional study examined the effect of Compound X on EGFR-mediated signaling in cultured epithelial cancer cells. Cells were treated with increasing concentrations of Compound X, and phosphorylation of downstream signaling proteins was measured using a western blot-based assay. The compound reduced pathway activation in a dose-dependent manner and decreased cell proliferation at higher concentrations. These findings suggest that Compound X may inhibit EGFR-dependent signaling. However, additional studies would be required to evaluate target specificity, off-target toxicity, and whether the observed effects occur in other cell types.
```

## Later Version: Public Abstracts

For a more realistic version, use public abstracts from:

- PubMed
- journal abstract pages
- open-access article abstracts

Recommended search terms:

```text
PubMed EGFR inhibitor abstract
PubMed drug target cell viability abstract
PubMed beta-lactamase inhibitor abstract
```

Important:

- Use abstracts and citations responsibly.
- Do not copy full papers into the app.
- For PDFs, start later only after the basic abstract version works.

---

# Required Output Structure

The AI summary should follow a fixed structure:

```markdown
## Research Question
...

## Drug Target
...

## Biological System
...

## Experimental Methods
...

## Key Findings
...

## Limitations
...

## Terms to Learn
...

## What to Verify Manually
...
```

## Optional JSON Output

For more structured processing, the AI can return:

```json
{
  "research_question": "",
  "drug_target": "",
  "biological_system": "",
  "methods": [],
  "key_findings": [],
  "limitations": [],
  "terms_to_learn": [],
  "manual_verification": []
}
```

Markdown is easier for the first version.

---

# Suggested Python Functions

```python
def build_summary_prompt(title, abstract):
    pass

def summarize_abstract(title, abstract):
    pass

def extract_key_terms(summary_text):
    pass

def build_verification_checklist(summary_text):
    pass
```

If no LLM API is used at first, create a rule-based placeholder that returns a template.

---

# Gradio Demo Requirements

## App Name

**TargetReader AI**

## Subtitle

**Understand drug target papers faster**

## Interface Layout

Recommended tabs:

1. Paste Abstract
2. Structured Summary
3. Key Terms
4. Ask Follow-up
5. Verification Checklist

## Fancy UI Elements

Include:

- hero title with emoji, such as `📄 TargetReader AI`
- example abstract button
- summary card
- key terms chips or bullet list
- methods explanation box
- verification checklist
- chatbot panel
- warning that AI may make mistakes

## Example Verification Checklist

```text
Check whether the drug target is correctly identified.
Check whether the assay method is described accurately.
Check whether the AI confused correlation with causation.
Check whether the limitation is stated in the abstract or inferred.
Check the original source before using the summary in academic work.
```

---

# Quarto Report Requirements

## Report Title

**TargetReader AI: AI-assisted Literature Reading Report**

## Suggested Sections

1. Overview
2. Why Scientific Papers Are Difficult
3. Responsible Use of AI
4. Example Abstract
5. Summary Output
6. Key Terms
7. Verification Checklist
8. Risks of AI Hallucination
9. Limitations
10. Future Improvements
11. What I Learned

## Fancy Quarto Features

Use:

- callout warnings
- tabsets for original vs summarized text
- code folding
- screenshots
- key term cards

Example callout:

```markdown
::: {.callout-warning}
## AI Caution
The AI-generated summary is a learning aid. It must not replace reading the original paper or verifying important scientific claims.
:::
```

---

# Recommended README Content

The README should include:

- what the app does
- example abstract
- screenshot of summary output
- responsible AI warning
- how to run locally
- limitations
- future improvements

---

# Student Learning Goals

By completing this project, the student should learn:

- how to structure a scientific paper summary
- how to ask better AI questions
- how to identify drug target, method, finding, and limitation
- why AI output needs verification
- how to build a simple Gradio text app
- how to present a literature-reading workflow in Quarto

---

# Vibe Coding Prompt

```text
I am a third-year Biochemistry student learning to use AI responsibly for scientific literature reading.

I want to build a project called TargetReader AI.

Please create beginner-friendly Python code with these files:
src/literature_ai.py
app.py

The Gradio app should:
1. accept a paper title and abstract
2. generate a structured summary
3. identify the drug target if present
4. identify methods, key findings, limitations, and terms to learn
5. create a manual verification checklist
6. include an example fictional abstract
7. include a warning that AI output must be verified

Please keep the code modular and explain each function in simple language.
```

---

# Success Criteria

Minimum success:

- App accepts title and abstract.
- App returns structured summary.
- App includes verification warning.

Good success:

- App has a clean Gradio UI.
- Quarto report is generated.
- Student can explain the difference between summary and verification.

Excellent success:

- App includes follow-up Q&A.
- App supports multiple paper summaries.
- App is deployed and linked from a Quarto portfolio.

---

# Visual and Interaction Enhancements

## Required Visuals

TargetReader AI should include:

- paper summary cards
- key term chips
- verification checklist
- original vs AI summary tabs
- chatbot-style follow-up panel

## Recommended Summary Cards

```text
Research Question
Drug Target
Biological System
Experimental Methods
Key Findings
Limitations
Terms to Learn
What to Verify Manually
```

## Interaction Ideas

Add:

```text
Summary level dropdown:
- Simple
- Undergraduate Biochemistry
- Research Assistant

Buttons:
- Generate Structured Summary
- Explain Key Terms
- Generate Verification Checklist
- Ask Follow-up Question
```

## Quarto Visual Additions

Include:

- side-by-side original abstract vs structured summary
- workflow diagram: Abstract → LLM summary → key terms → verification checklist
- callout warning about hallucination risk


---

# Academic Biochemistry Support Add-On

TargetReader AI should support academic paper-reading practice, not only AI summarization.

## Academic Concepts

TargetReader AI should help the student understand:

```text
research question
biological system
experimental method
key finding
limitation
scientific vocabulary
journal club discussion
responsible academic use of AI
```

## Academic Output Buttons

Recommended Gradio buttons:

```text
Generate Journal Club Notes
Explain Key Terms
Generate Discussion Questions
Generate Presentation Outline
```

## Academic Challenge Questions

```text
1. What is the research question?
2. What biological system was studied?
3. What method was used?
4. What is the main finding?
5. What is the main limitation?
6. What should be verified in the full paper?
```

## Recommended Academic Output

The app should be able to generate:

```text
structured paper summary
key terms list
journal club notes
methods explanation
discussion questions
presentation outline
what to verify in the full paper
```

This makes TargetReader AI useful for both literature-reading workflows and academic life science study.
