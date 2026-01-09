# Interpretable Multi-Modality Consensus QSAR Framework: Integrating Machine and Deep Learning for Enhanced Multi-Endpoint Toxicity Assessment

**Authors:**  
FAUZAN SYARIF NURSYAFI¹, MUHAMMAD ADNAN PRAMUDITO², YUNENDAH NUR FUADAH³, and KI MOO LIM¹,⁴,⁵**  

¹ Computational Medicine Lab, Department of Medical IT Convergence Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
² Computational Medicine Lab, Department of IT Convergence Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
³ Telecommunication Engineering Study Program, School of Electrical Engineering, Telkom University Main Campus, Bandung, Indonesia  
⁴ Computational Medicine Lab, Department of Biomedical Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
⁵ Meta Heart Co., Ltd, Gumi, 39253, Republic of Korea  

**Corresponding authors:** [kmlim@kumoh.ac.kr](mailto:kmlim@kumoh.ac.kr)

---

## 🧩 Overview
This repository contains the code for developing and evaluating QSAR (Quantitative Structure–Activity Relationship) models for **multi-endpoint chemical toxicity prediction** using an **interpretable multi-modality consensus framework**.

📌 **Supplementary Materials**  
Comprehensive methodological details, dataset sources, descriptor definitions, hyperparameter configurations, and additional results are provided in:

- **`Supplementary Online Materials.docx`**

This document should be consulted alongside the notebooks and manuscript to ensure full reproducibility and transparency.

---

## 🧠 Toxicity Endpoints
The framework covers **8 mechanistically distinct toxicity endpoints**, comprising **30,160 unique compounds**, following the original training, test, and external validation splits reported in the source datasets:

1. Skin Sensitization  
2. Respiratory Toxicity  
3. AMES Mutagenicity  
4. Hepatotoxicity  
5. Developmental Toxicity  
6. Cardiotoxicity  
7. Drug-Induced Nephrotoxicity (DIN)  
8. Neurotoxicity  

---

## ⚙️ Framework Integration

### Molecular Representations
- **Fingerprints:** Morgan, MACCS, Atom Pair Fingerprints (APF)  
- **Physicochemical descriptors:** RDKit- and CDK-derived properties  

### Learning Algorithms
- Random Forest (RF)  
- XGBoost (XGB)  
- Support Vector Machine (SVM)  
- Deep Neural Network (DNN)  

### Model Evaluation
- Stratified **10-fold cross-validation** on training data  
- Independent test and external validation sets  
- Performance metrics: **AUC, ACC, BACC, SEN, SPE**, with **95% bootstrap confidence intervals**

### Consensus Modeling
- Single-algorithm descriptor consensus  
- Multi-algorithm, multi-modality **AUC-weighted consensus**

---

## 🧠 Explainability & Reliability Analysis
- SHAP-based explainable AI (XAI) for global and local feature attribution  
- Structure contribution map analysis for fingerprint-based models  
- Applicability domain (AD) assessment:
  - Tanimoto similarity-based AD for fingerprints  
  - Leverage/Williams plot-based AD for physicochemical descriptors  
- UMAP-based chemical space visualization of training, test, and external compounds  

---

## 📂 Repository Structure & Notebooks

### 1️⃣ Descriptor Computation & Data Preprocessing  
**`Descriptor Computation_Preprosesing data.ipynb`**
- Structure standardization (salts/solvents removal, charge normalization, tautomer handling)  
- Descriptor generation (MACCS, Morgan, APF, RDKit–CDK)  
- Label harmonization and export of QSAR-ready datasets  

---

### 2️⃣ Machine Learning Model Training (10-fold CV)  
**`Training_ML_10foldCrossvalidation.ipynb`**
- Training RF, XGB, and SVM models for each descriptor modality  
- Stratified 10-fold cross-validation  
- Model selection based on cross-validated AUC  

---

### 3️⃣ Deep Neural Network Training (10-fold CV)  
**`Training_DNN_10foldCrossvalidation.ipynb`**
- Construction of DNN architectures for each descriptor type  
- Stratified 10-fold cross-validation  
- Regularization and early stopping  
- Saving trained models for downstream consensus modeling  

---

### 4️⃣ Model Evaluation & Consensus Construction  
**`Performance_Model_Evaluation.ipynb`**
- Loading trained base models  
- Construction of single- and multi-modality consensus models  
- Evaluation on independent test and external validation sets  
- Generation of final performance tables and figures  

---

### 5️⃣ Chemical Space & Applicability Domain Analysis  
**`Chemical Space_AD Analysis_Consensus.ipynb`**
- Applicability domain assessment for individual and consensus models  
- UMAP-based visualization of chemical space coverage  

---

### 6️⃣ Explainable AI (SHAP) Analysis  
**`SHAP Analysis.ipynb`**
- Global feature importance analysis  
- Descriptor- and bit-level contribution interpretation  
- Identification of key structural alerts associated with toxicity  

---

## 🧮 Dependencies
| Package | Version |
|--------|---------|
| Python | 3.x |
| RDKit | 2025.3.2 |
| CDK-pywrapper | 0.1.1 |
| scikit-learn | 1.6.1 |
| NumPy | 2.1.3 |
| Pandas | 2.2.3 |
| install-jdk | 0.3.0 |
| bounded-pool-executor | 0.0.3 |

---

## 🧾 Notes
This repository corresponds to the manuscript:

**“Interpretable Multi-Modality Consensus QSAR Framework Integrating Machine and Deep Learning for Enhanced Multi-Endpoint Toxicity Assessment.”**

Additional methodological details, descriptor lists (Table S1), hyperparameter settings (Table S2), and dataset references are provided in the **Supplementary Online Materials**.

---

## 📚 Citation
Citation details will be updated upon publication.

---

## 🧠 Acknowledgments
This work was conducted at the **Computational Medicine Lab**, Kumoh National Institute of Technology, Gumi, Republic of Korea.
