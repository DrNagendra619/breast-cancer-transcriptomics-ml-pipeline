# 🧬 Breast Cancer Transcriptomics & Machine Learning Pipeline

## Integrated Bioinformatics Framework for Biomarker Discovery and Therapeutic Target Identification

---

## 📌 Repository Description

Integrated transcriptomic and machine learning pipeline for breast cancer biomarker discovery, drug–gene interaction analysis, and ADMET-based therapeutic prioritization.

---

# 📖 Overview

Breast cancer is a highly heterogeneous disease characterized by complex molecular mechanisms and diverse therapeutic responses. Traditional biomarker discovery studies frequently rely on single-cohort datasets, which often introduce platform bias and limit cross-study reproducibility.

This project presents an **integrated multi-cohort transcriptomic and machine learning framework** designed to identify robust diagnostic biomarkers and potential therapeutic targets in breast cancer.

The pipeline integrates **gene expression analysis, machine learning feature selection, network biology, pharmacogenomics validation, and chemoinformatics modeling** to bridge molecular discovery with potential therapeutic intervention strategies.

The workflow combines **bioinformatics, artificial intelligence, and pharmacological data integration** to provide a reproducible computational pipeline for precision oncology research.

---

# 🧠 Key Study Highlights

✔ Integration of **five independent transcriptomic datasets**

✔ Identification of **14,184 consensus genes**

✔ Machine learning-based biomarker discovery using **Random Forest**

✔ Extraction of **Top 50 predictive biomarkers**

✔ Network biology analysis identifying **10 regulatory hub genes**

✔ Drug–gene interaction network construction

✔ Pharmacogenomic validation using **GDSC drug sensitivity data**

✔ ADMET filtering of therapeutic compounds

✔ Machine learning prediction of **drug solubility properties**

---

# 📊 Datasets Used

The study integrates five publicly available breast cancer microarray datasets from the **NCBI Gene Expression Omnibus (GEO)**.

| GEO Dataset | Samples | Study Objective                   |
| ----------- | ------- | --------------------------------- |
| GSE20685    | 327     | Tumor heterogeneity               |
| GSE2990     | 189     | Disease recurrence                |
| GSE42568    | 121     | Survival prediction               |
| GSE54002    | 433     | Tumor vs normal tissue            |
| GSE41998    | 279     | Neoadjuvant chemotherapy response |

These datasets collectively represent multiple biological and clinical endpoints including tumor heterogeneity, treatment response, and patient survival.

---

# 🔬 Computational Workflow

```
GEO Data Collection
        ↓
Microarray Normalization and Processing
        ↓
Gene Annotation using gProfiler
        ↓
Multi-Cohort Gene Intersection
        ↓
14,184 Consensus Genes Identified
        ↓
Machine Learning Feature Selection
(Random Forest)
        ↓
Top 50 Predictive Biomarkers
        ↓
Protein-Protein Interaction Network
(STRING + Cytoscape)
        ↓
10 Hub Gene Network
        ↓
Drug-Gene Interaction Network
(DGIdb + Cytoscape)
        ↓
Pharmacogenomic Validation
(GDSC Drug Sensitivity Data)
        ↓
SMILES Conversion of Drug Compounds
        ↓
ADMET Filtering (SwissADME)
        ↓
Machine Learning Prediction of Drug Solubility
```

---

# 🧬 Core Biological Findings

## Consensus Gene Signature

Integration of the five independent datasets resulted in **14,184 universally conserved genes** across all cohorts.
These genes served as the input feature space for downstream machine learning analysis.

---

## Machine Learning Biomarker Discovery

Six regression algorithms were benchmarked to identify predictive biomarkers:

* Random Forest
* Gradient Boosting
* Support Vector Regression
* K-Nearest Neighbors
* Linear Regression
* Decision Trees

The **Random Forest model achieved the best performance** and was used for feature importance ranking.

### Model Performance

| Model                     | R² Score |
| ------------------------- | -------- |
| Random Forest             | 0.736    |
| Gradient Boosting         | 0.704    |
| Support Vector Regression | 0.692    |
| K-Nearest Neighbors       | 0.691    |
| Linear Regression         | 0.660    |
| Decision Tree             | 0.551    |

Using Random Forest feature importance, the analysis isolated the **Top 50 predictive biomarkers**.

---

# 🧬 Hub Gene Network

Protein-protein interaction analysis using STRING and Cytoscape identified **10 master regulatory hub genes**:

```
ESR1
TOP2A
TPX2
KIF4A
MELK
NCAPG
NEK2
RRM2
ASPM
FN1
```

These genes play key roles in:

* mitotic cell cycle regulation
* chromosome segregation
* estrogen receptor signaling
* tumor proliferation

---

# 🧪 Prognostic Biomarker Identification

Survival analysis using TCGA data via the **GEPIA2 platform** identified **KIF4A** as a significant prognostic biomarker.

High KIF4A expression is associated with:

* poor overall survival
* aggressive tumor progression
* mitotic dysregulation

KIF4A therefore represents a potential **therapeutic and diagnostic biomarker** for breast cancer.

---

# 💊 Drug–Gene Interaction Network

Drug–gene interactions were extracted using **DGIdb** and visualized in Cytoscape.

Two key therapeutic agents were identified as major interactors:

### Lapatinib

EGFR / ERBB2 inhibitor used in HER2-positive breast cancer.

### Tamoxifen

Selective estrogen receptor modulator widely used in hormone receptor-positive breast cancer.

Drug response validation was performed using **GDSC breast cancer cell line sensitivity data (IC50)**.

---

# 🧪 Chemoinformatics Drug Filtering

Initial pharmacogenomic dataset:

```
288 unique drug compounds
```

After SMILES validation:

```
232 structurally verified compounds
```

After ADMET filtering:

```
96 pharmacokinetically compliant drug candidates
```

ADMET descriptors included:

* molecular weight
* lipophilicity
* topological polar surface area
* gastrointestinal absorption
* CYP450 inhibition
* blood-brain barrier permeability

---

# 🤖 Machine Learning for Drug Property Prediction

Machine learning models were used to predict **aqueous solubility (ESOL LogS)** of candidate compounds.

| Model             | R² Score | RMSE  |
| ----------------- | -------- | ----- |
| Ridge Regression  | 0.9867   | 0.178 |
| Gradient Boosting | 0.9864   | 0.179 |
| Random Forest     | 0.9757   | 0.240 |
| ElasticNet        | 0.9572   | 0.318 |
| KNN               | 0.7723   | 0.735 |
| SVR               | 0.657    | 0.903 |

The **Ridge Regression model demonstrated the highest predictive accuracy**.

---

# 🔬 Targeted Biological Pathways

Optimized drug candidates primarily target key oncogenic pathways:

| Target Pathway                | Frequency |
| ----------------------------- | --------- |
| PI3K / MTOR signaling         | 10        |
| Chromatin histone methylation | 8         |
| Genome integrity pathways     | 8         |
| DNA replication               | 7         |
| WNT signaling                 | 6         |

These pathways correspond with the **cell-cycle and oncogenic signaling dysregulation observed in the hub gene network**.

---

# 🧰 Technologies and Tools

## Programming Languages

* Python
* R

## Python Libraries

* scikit-learn
* pandas
* numpy
* matplotlib

## Bioinformatics Platforms

* GEO (Gene Expression Omnibus)
* STRING database
* Cytoscape
* DGIdb
* GEPIA2
* Enrichr
* SwissADME
* GDSC database

---

# 📂 Repository Structure

```
breast-cancer-transcriptomics-ml-pipeline

data/
    GEO_metadata.csv

notebooks/
    DEG_analysis.ipynb
    RandomForest_feature_selection.ipynb
    ADMET_analysis.ipynb

scripts/
    data_processing.R
    feature_selection.py

figures/
    workflow.png
    volcano_plots.png
    ppi_network.png

results/
    volcano_plots
    PPI_network
    DGI_network
    survival_analysis
```

---

# 🚀 Applications

This computational framework can be adapted for:

* cancer biomarker discovery
* precision oncology research
* multi-omics data integration
* pharmacogenomics analysis
* drug sensitivity prediction
* therapeutic target identification

---

# 📚 Citation

If you use this analysis pipeline or dataset integration approach, please cite:

Nagendra
Integrated Transcriptomic and Machine Learning Approach for Breast Cancer Biomarker Discovery and Therapeutic Target Identification.

---

# 👨‍🔬 Author

Dr. Nagendra
Clinical Data Science
Bioinformatics • Machine Learning • Precision Oncology

---

# 📜 License

This project is licensed under the MIT License.
