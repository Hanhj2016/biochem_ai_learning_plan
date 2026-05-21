# GeneShift: Mini Gene Expression Explorer

## Project Summary

**GeneShift** is a mini computational biology project that analyzes a simplified gene expression dataset.

It introduces the student to concepts such as control vs treatment comparison, fold change, up-regulated genes, down-regulated genes, and cautious biological interpretation.

## Project Positioning

> A beginner-friendly gene expression explorer for understanding treatment-driven expression changes.

This is more advanced than BioDose, ProteinLens, and TargetReader. It is best as a second-stage or optional project.

---

# Why This Project Matters

Computational biology often involves comparing biological conditions.

Typical questions include:

- Which genes change after treatment?
- Which genes are up-regulated?
- Which genes are down-regulated?
- Which genes may be biologically important?
- What should be verified using biological databases or literature?

This project gives a simple introduction without requiring a full RNA-seq pipeline.

---

# Key Use Cases

## Use Case 1: Control vs Treatment Gene Expression

### Input

A CSV file with gene expression values for control and treatment replicates.

### Output

- control mean
- treatment mean
- fold change
- log2 fold change
- top up-regulated genes
- top down-regulated genes

## Use Case 2: Top Gene Visualization

### Input

Expression summary table.

### Output

- top changed gene bar chart
- optional heatmap-style chart
- ranked gene table

## Use Case 3: AI-assisted Biological Notes

### Input

Top changed genes.

### Output

- possible biological relevance
- terms to learn
- databases to check
- manual verification checklist

---

# Test Data Source

## First Version: Synthetic Data

Use synthetic toy data first.

Reason:

- real RNA-seq workflows are complex
- real datasets require normalization and quality control
- beginner version should focus on concepts
- synthetic data is easier for demo

## Synthetic Data Generation Prompt

```text
Generate a small synthetic gene expression CSV dataset for a beginner computational biology project.

The dataset should have 12 genes and 6 samples:
control_1, control_2, control_3, treatment_1, treatment_2, treatment_3.

Include genes related to cancer, apoptosis, inflammation, and housekeeping controls.

Some genes should be up-regulated in treatment.
Some genes should be down-regulated.
Some housekeeping genes should stay stable.

Columns:
gene, control_1, control_2, control_3, treatment_1, treatment_2, treatment_3

Return only CSV content.
```

## Example Synthetic Data

```csv
gene,control_1,control_2,control_3,treatment_1,treatment_2,treatment_3
EGFR,10.2,9.8,10.5,16.5,17.1,15.9
TP53,8.1,8.4,8.0,12.2,11.8,12.5
MYC,15.0,14.8,15.3,21.4,22.1,20.9
GAPDH,30.2,30.1,29.8,30.5,30.0,30.3
ACTB,25.1,25.4,24.9,25.2,25.0,25.5
BCL2,6.2,6.5,6.1,3.1,3.3,2.9
CASP3,4.5,4.7,4.4,8.8,9.1,8.5
IL6,2.1,2.3,2.0,7.5,7.8,7.2
TNF,3.2,3.0,3.4,6.9,7.1,6.7
VEGFA,5.4,5.6,5.5,9.8,10.1,9.5
CDKN1A,4.8,5.0,4.7,9.2,9.5,8.9
MKI67,13.5,13.8,13.2,7.1,7.4,6.8
```

## Later Version: Public Dataset

For a later version, use public datasets from sources such as:

- NCBI GEO
- ArrayExpress
- Kaggle educational gene expression datasets

Recommended search terms:

```text
GEO gene expression control treatment CSV
public gene expression dataset cancer treatment
beginner gene expression dataset CSV
```

Important:

- Real gene expression analysis requires normalization.
- Do not claim biological conclusions from toy data.
- Avoid full RNA-seq pipeline at the beginner stage.

---

# Required Analysis

The project should:

1. Load expression CSV.
2. Identify control columns.
3. Identify treatment columns.
4. Calculate control mean.
5. Calculate treatment mean.
6. Calculate fold change.
7. Calculate log2 fold change.
8. Sort top up-regulated genes.
9. Sort top down-regulated genes.
10. Plot top changed genes.
11. Generate cautious biological notes.

---

# Suggested Python Functions

```python
def load_expression_data(csv_file):
    pass

def calculate_expression_summary(df):
    pass

def get_top_changed_genes(summary_df, n=5):
    pass

def create_fold_change_plot(summary_df):
    pass

def generate_gene_notes(top_genes):
    pass
```

---

# Gradio Demo Requirements

## App Name

**GeneShift**

## Subtitle

**Explore treatment-driven gene expression changes**

## Interface Layout

Recommended tabs:

1. Upload Expression Data
2. Fold Change Table
3. Top Genes
4. Visualization
5. AI Biological Notes

## Fancy UI Elements

Include:

- hero title with emoji, such as `🧬 GeneShift`
- example dataset button
- top up-regulated genes card
- top down-regulated genes card
- fold-change table
- bar chart
- optional heatmap-style plot
- AI interpretation card
- normalization warning

## Example Warning

```text
This is a simplified toy analysis. Real gene expression analysis requires proper normalization, quality control, batch effect assessment, and biological validation.
```

---

# Quarto Report Requirements

## Report Title

**GeneShift: Mini Gene Expression Analysis Report**

## Suggested Sections

1. Overview
2. What Gene Expression Means
3. Dataset Description
4. Methods
5. Fold Change Analysis
6. Top Up-regulated Genes
7. Top Down-regulated Genes
8. Visualization
9. AI-assisted Biological Notes
10. Limitations
11. Future Improvements
12. What I Learned

## Fancy Quarto Features

Use:

- callout warnings
- fold-change chart
- top gene tables
- code folding
- table of contents

Example callout:

```markdown
::: {.callout-warning}
## Simplified Analysis
This project uses a toy dataset and simplified fold-change calculations. Real gene expression studies require normalization and statistical testing.
:::
```

---

# Recommended README Content

The README should include:

- project overview
- example dataset
- screenshot of Gradio app
- screenshot of Quarto report
- simplified analysis warning
- how to run locally
- future improvements

---

# Student Learning Goals

By completing this project, the student should learn:

- what gene expression data looks like
- what control and treatment groups mean
- what fold change means
- why log2 fold change is useful
- how to identify top changed genes
- why biological interpretation requires caution
- how computational biology differs from simple data plotting

---

# Vibe Coding Prompt

```text
I am a third-year Biochemistry student learning computational biology with Python and AI assistance.

I want to build a project called GeneShift.

The input CSV has columns:
gene, control_1, control_2, control_3, treatment_1, treatment_2, treatment_3

Please create beginner-friendly Python code with these files:
src/gene_expression.py
src/plots.py
app.py

The Gradio app should:
1. upload a gene expression CSV
2. calculate control mean and treatment mean
3. calculate fold change and log2 fold change
4. identify top up-regulated and down-regulated genes
5. create a bar chart
6. generate cautious biological notes
7. include a warning about toy data and normalization

Please keep the code modular and explain each function in simple language.
```

---

# Success Criteria

Minimum success:

- CSV upload works.
- Fold change table is generated.
- Top genes are displayed.
- Plot is generated.

Good success:

- App looks polished.
- Quarto report is generated.
- Student can explain why this is not a full RNA-seq analysis.

Excellent success:

- App supports real small public datasets.
- App includes normalization discussion.
- App is deployed and linked from portfolio.

---

# Visual and Interaction Enhancements

## Required Visuals

GeneShift should include:

- fold-change bar chart
- top up-regulated genes card
- top down-regulated genes card
- heatmap-style chart if possible
- normalization warning

## Recommended Result Cards

```text
Number of genes
Top up-regulated gene
Top down-regulated gene
Stable housekeeping genes
Synthetic or real dataset badge
```

## Recommended Interactive Chart

```text
x-axis: gene
y-axis: log2 fold change
hover: control mean, treatment mean, fold change, log2 fold change
```

## Data Quality Warnings

Show warnings for:

```text
missing gene column
missing control columns
missing treatment columns
non-numeric expression values
too few replicates
very small dataset
```

## Quarto Visual Additions

Include:

- fold-change chart
- top gene table
- workflow diagram: expression table → fold change → top genes → AI notes → verification
- callout warning about simplified toy analysis


---

# Academic Biochemistry Support Add-On

GeneShift should support academic Biochemistry and life science learning, not only simplified computational analysis.

## Academic Concepts

GeneShift should help the student understand:

```text
gene expression
control vs treatment comparison
fold change
log2 fold change
up-regulation and down-regulation
housekeeping genes
normalization
limits of simplified expression analysis
```

## Academic Output Buttons

Recommended Gradio buttons:

```text
Generate Lab Report Section
Generate Figure Caption
Generate Study Questions
Generate Next Experiment Suggestions
```

## Academic Challenge Questions

```text
1. What does fold change mean?
2. Why is log2 fold change often used?
3. What is an up-regulated gene?
4. What is a housekeeping gene?
5. Why is normalization important?
6. Why should we avoid treating this toy analysis as a full RNA-seq result?
```

## Recommended Academic Output

The app should be able to generate:

```text
gene expression summary
fold-change figure caption
biological interpretation draft
limitations section
study questions
next experiment suggestions
```

This makes GeneShift useful for both computational biology practice and academic Biochemistry learning.
