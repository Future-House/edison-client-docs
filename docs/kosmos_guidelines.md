# Best Practices for Optimizing Kosmos Workflows

Kosmos is a data-driven discovery agent. To get the most out of each Kosmos run, we recommend following these guidelines:

## 1. Provide a clear and feasible research objective that requires iteration.
The research objective can be broad and exploratory or focused and hypothesis-driven. While Kosmos can handle multiple objectives, it performs best with a single, well-defined objective. It should have scope for iterative hypothesis generation and testing. The answer should not be obvious after reading a few papers or conducting a single data analysis. A scientific collaborator in a relevant field should be able to reasonably complete the task within weeks or months.‍

## 2. Provide enough context in the research objective.
The research objective should provide sufficient scientific and experimental context as a starting point for data analysis or literature search. While Kosmos is able to conduct literature search and read all provided datasets, it will greatly benefit from context highlighting nuances unique to your research group, such as key experimental design choices, non-obvious assumptions common in the field, or atypical data-handling protocols. Phrase it as you would explain to an experienced colleague who just joined your team.

Here are some examples of ways to improve research objective prompts:

### Inappropriate research objectives‍
- Which of these tissue have a lower ECM pathway expression score?

- List all the genes that are differentially expressed (p < 0.05) between the 'control' and 'drought' RNA-seq samples.

- How is graphene used for water desalination? Suggest cross-linking agents that is compatible with our method.

- Analyze the attached county-level public health dataset. Does ice cream consumption correlate with asthma rates?

### Good research objectives
- Compare ECM pathway expression levels in the melanoma tissue samples. Propose hypotheses on mechanisms driving these changes and downstream functional consequences.

- Analyze the RNA-seq dataset provided from Arabidopsis thaliana leaves, comparing 'control' (well-watered) to 'drought' (water withholding) samples across a time course. Identify the ****key regulatory pathways that mediate acclimation. Are there any transcription factor(s) outside the well-known ABA pathway that may be a master regulator of this response?

- We are investigating the use of laminated graphene oxide (GO) membranes for water desalination. A major problem is that these membranes swell and lose selectivity when hydrated. I have attached our recent experimental results showing interlayer spacing vs. salt rejection. Identify the top 3-5 most promising cross-linking agents (e.g., diamines, metal ions) that have been proven to control GO membrane swelling and propose which one would be most compatible with our current layer-by-layer fabrication method.

- The provided county-level public health dataset includes data on disease prevalence, environmental factors, and socio-demographics. Our central hypothesis is that counties with higher air pollution (PM2.5) will have increased asthma prevalence, but we suspect this effect is strongest in low-income communities. Build a regression model to test this hypothesis. Control for confounding variables: this must include population density, average age, and regional differences in pollen, so please treat these as covariates. Propose a follow-up analysis to explore the specific impact of pollen vs. PM2.5.

## 3. Provide sufficient context in the data description.
Ensure that Kosmos has the necessary context about the data provided. For example, if providing a table, ensure all column names are intuitively labeled, or provide an additional sheet that describes what each column name means in more detail. A scientific collaborator in a relevant field should be able to interpret the data with the provided research objective without seeking further clarification.

## 4. Provide complex data.
While Kosmos can operate on simple data (e.g. a csv containing a list of gene names), Kosmos make the most interesting discoveries when given complex high dimensional data, such as scRNA-seq, proteomics, or environmental parameters across multiple samples or timepoints. You can also provide multiple datasets that are relevant to the research objective. There is no limit on the number of files you provide Kosmos as long as total uncompressed size of your dataset is under 5GB. Kosmos is capable of managing workspaces with 100s of files.

## 5. Provide properly labeled and processed data.
The dataset is used as a starting point for exploratory analysis. While Kosmos can perform quality control steps and is able to correct for artifacts such as batch effects, Kosmos is most powerful when operating on high quality, processed data. We do not recommend getting Kosmos to process your data such as mapping of raw sequencing files or annotating raw imaging data.

## 6. Iterate.
Take some time to write your first Kosmos query so you can avoid the common fallacies listed above. However, trial and error will be your best guide to develop a deep intuition on how to best use the system. Start with a familiar dataset or topic. Since runtime scales with dataset size, begin small for faster results and quicker iteration.