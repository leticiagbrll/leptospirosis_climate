# Leptospirosis and Climate Analysis in Brazilian Capitals (2008–2023)

This repository contains the full workflow used to analyze the association between **meteorological variables** and **leptospirosis incidence** in Brazilian capitals from 2008 to 2023.  
The project follows **open science and reproducible research practices**, using Python and R collaboratively.

---

## 📦 Dataset

The integrated epidemiological + climatic dataset used in all analyses is publicly available at Zenodo:

**DOI:** https://doi.org/10.5281/zenodo.17734843

---

## 🧠 Project Workflow

The analysis pipeline is structured into three main stages:

### 1️⃣ Data Integration (Python – Google Colab)

**Directory:** `01_data_integration/`

**Notebook:**  
- `01_data_integration_sinan_inmet.ipynb`  
  - Extraction of SINAN annual CSVs  
  - Extraction of INMET hourly weather data  
  - Cleaning and harmonization of variables  
  - Monthly aggregation of climatic metrics  
  - Standardization of capital/state identifiers  
  - Merge of epidemiological + weather data  
  - **Output:** `base_integrada_leptospirose_2008-2023.csv`

---

### 2️⃣ Statistical Analyses (R – RMarkdown)

**Directory:** `02_statistical_analysis/`

**File:**  
- `02_statistical_test_glm_analysis.Rmd`  
  - Descriptive statistics  
  - Time-series exploration  
  - Spearman correlation  
  - Negative Binomial GLM (`MASS::glm.nb`)  
  - Model selection (AIC)  
  - Residual diagnostics  
  - Export of model coefficients and fitted values  
  - **Output:** tables, diagnostics, and model parameters

---

### 3️⃣ Model Interpretability (Python – SHAP)

**Directory:** `03_interpretability/`

**Notebook:**  
- `03_glm_shap_interpretation.ipynb`  
  - Import results from the R model  
  - Build equivalent model structure in Python  
  - Compute SHAP values  
  - Feature importance and dependence plots  
  - Interpretability visualizations

---

## 🔁 Reproducibility Instructions

### Python Requirements

Install via the provided `requirements.txt`:

```bash
pip install -r requirements.txt
```
Or manually:
```bash
pip install pandas numpy matplotlib seaborn shap statsmodels scipy
```
### R Requirements

```bash
install.packages(c("MASS", "stats", "dunn.test", "ggplot2"))
```


---

## 📜 License

This project is licensed under **CC BY 4.0**, allowing reuse with attribution.

---

## 👩‍💻 Authors

- **Rubia Diaz Taveiros Kuhne**  
- **Letícia Gabrielle Souza**

