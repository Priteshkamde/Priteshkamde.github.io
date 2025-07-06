---
layout: post
title: "Cancer Subtype Classifier using Gene Expression"
author: pritesh
categories: [Python, Bioinformatics]
image: /assets/images/cancer-demo-header.png
tags: [sticky, featured]
---

# 🎯 Cancer Subtype Classifier – Demo using Gene Expression and ML

### 🧩 Problem Statement

In cancer genomics, identifying the **cancer subtype** of a tumor sample is crucial for:

- Accurate diagnosis
- Treatment planning
- Precision medicine research

However, high-dimensional RNA-seq data makes subtype classification challenging, especially across multiple cancer types.

---

### ❓ Why Are We Solving This?

Automatically classifying tumor samples based on gene expression can:

- Help researchers label or validate samples
- Support oncologists with second-opinion diagnostics
- Serve as a preprocessing layer for further mutation or survival analysis

---

### Approach

We built a **multi-class machine learning classifier** that:

1. Takes a tumor sample's RNA-seq gene expression (20,531 genes)
2. Predicts the primary cancer type (subtype)
3. Visualizes performance, top genes, and live predictions

---

### Dataset

We used the **TCGA-PANCAN-HiSeq-801x20531** dataset:

- **Samples:** 801 tumor samples
- **Genes:** 20,531 (RNA-Seq HiSeq platform)
- **Source:** The Cancer Genome Atlas (TCGA)
- **Format:** CSV matrix (samples × genes) with labels

Cancer types in this pancancer set include:

- `BRCA` – Breast invasive carcinoma
- `COAD` – Colon adenocarcinoma
- `LUAD` – Lung adenocarcinoma
- `KIRC` – Kidney renal clear cell carcinoma
- `HNSC` – Head and neck squamous cell carcinoma
- `OV` – Ovarian serous cystadenocarcinoma
- `THCA` – Thyroid carcinoma  
  ...and others

---

### Tech Stack

| Component              | Tool                            |
| ---------------------- | ------------------------------- |
| Machine Learning Model | **XGBoost Classifier**          |
| Label Encoding         | **scikit-learn LabelEncoder**   |
| Pipeline               | **scikit-learn Pipeline**       |
| Dashboard UI           | **Streamlit**                   |
| Data Processing        | **pandas, seaborn, matplotlib** |
| Model Persistence      | **joblib**                      |

---

### Working

1. Load `data_small.csv` (trimmed gene matrix) and `labels.csv`
2. Encode cancer subtypes as numeric labels
3. Train an XGBoost classifier in a Scikit-learn pipeline
4. Save the trained pipeline (`classifier_pipeline.joblib`)
5. Load the model in a **Streamlit dashboard**:
   - View performance metrics
   - See top gene importances
   - Select a sample and get predicted cancer type

---

### Output

- ✅ Accuracy: ~85% on test data (varies by split)
- 🔬 Top genes shown by feature importance
- 🧠 Interactive Streamlit web app for exploration

---

![Cancer Subtype Classifier Demo](/assets/images/cancer-demo.png)
