# Interpretable Multi-Modality Consensus QSAR Framework: Integrating Machine and Deep Learning for Enhanced Multi-Endpoint Toxicity Assessment

**Authors:**  
FAUZAN SYARIF NURSYAFI¹, MUHAMMAD ADNAN PRAMUDITO², YUNENDAH NUR FUADAH³, and KI MOO LIM¹,⁴,⁵**  

¹ Computational Medicine Lab, Department of Medical IT Convergence Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
² Computational Medicine Lab, Department of IT Convergence Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
³ Telecommunication Engineering Study Program, School of Electrical Engineering, Telkom University Main Campus, Bandung, Indonesia  
⁴ Computational Medicine Lab, Department of Biomedical Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
⁵ Meta Heart Co., Ltd, Gumi, 39253, Republic of Korea  

📧 **Corresponding authors:** [kmlim@kumoh.ac.kr](mailto:kmlim@kumoh.ac.kr), [yunendah@telkomuniversity.ac.id](mailto:yunendah@telkomuniversity.ac.id)

---

## 🧩 Overview
This repository contains the code for developing and evaluating QSAR (Quantitative Structure–Activity Relationship) models for **multi-endpoint chemical toxicity prediction** using an **interpretable multi-modality consensus framework**.

### Framework Integration
- **Molecular fingerprints:** Morgan, MACCS, Atom Pair Fingerprints (APF)  
- **Physicochemical descriptors:** generated using RDKit and CDK  
- **Algorithms:** Random Forest (RF), XGBoost (XGB), Support Vector Machine (SVM), and Deep Neural Network (DNN)  

All models are trained under a **unified AUC-weighted consensus strategy** and evaluated using **stratified 10-fold cross-validation** on training sets and **independent test/external validation sets**.

---

## 🧠 Toxicity Endpoints
This study covers **8 toxicity endpoints** with a total of **30,160 unique compounds**, following the original splits from the reference datasets:

1. Skin Sensitization  
2. Respiratory Toxicity  
3. AMES Mutagenicity  
4. Hepatotoxicity  
5. Developmental Toxicity  
6. Cardiotoxicity  
7. Drug-Induced Nephrotoxicity (DIN)  
8. Neurotoxicity  

---

## ⚙️ Features

- **Unified Data Curation Pipeline**
  - Structure standardization (salts/solvents, tautomers, charge normalization)
  - Duplicate removal and label harmonization  

- **Descriptor Computation**
  - MACCS, Morgan, APF fingerprints  
  - RDKit–CDK physicochemical properties  

- **Model Training**
  - RF, XGB, SVM, and DNN models for each descriptor–algorithm combination  
  - Evaluation with **AUC, ACC, BACC, SEN, SPE** and **95% bootstrap confidence intervals**

- **Consensus Modeling**
  - Single-algorithm descriptor consensus  
  - Multi-algorithm multi-modality consensus (AUC-weighted)

- **Explainable AI (XAI)**
  - Global feature importance via **SHAP**  
  - Dependence plots for key bits/descriptors  

- **Applicability Domain & Chemical Space Analysis**
  - Tanimoto-based AD for fingerprints  
  - Leverage/Williams AD for physicochemical descriptors  
  - UMAP visualization for train vs test/external compounds  

- **Reproducible Environment**
  - Fixed library versions for consistent results  

---

## 🧮 Dependencies

| Package | Version |
|----------|----------|
| Python | 3.x |
| RDKit | 2025.3.2 |
| CDK-pywrapper | 0.1.1 |
| TensorFlow | 2.19.0 |
| scikit-learn | 1.6.1 |
| NumPy | 2.1.3 |
| Pandas | 2.2.3 |
| install-jdk | 0.3.0 |
| bounded-pool-executor | 0.0.3 |

---

## 🧰 Usage

### 1️⃣ Compute Descriptors
Use:  
`Descriptor_Computation_Preprocessing_data.ipynb`

Performs:
- Structure standardization (salts/solvents, charge normalization)
- Descriptor generation (MACCS, Morgan, APF, RDKit–CDK)
- Exports QSAR-ready feature matrices and labels for each endpoint

---

### 2️⃣ Train Models
Use:  
- `Training_ML_Fingerprint_10foldCrossvalidation.ipynb`  
- `Training_ML_PhysicochemicalProperties_10foldCrossvalidation.ipynb`

Performs:
- Stratified 10-fold CV for RF, XGB, SVM, and DNN using each descriptor modality  
- Selects top models based on cross-validated AUC for consensus integration  
- Preserves original train/test or external validation splits  

---

### 3️⃣ Evaluate & Build Consensus Models
Use:  
`Performance_Model_Evaluation.ipynb`

Performs:
- Loads trained base models  
- Builds single-algorithm and multi-modality AUC-weighted consensus models  
- Evaluates on independent test/external validation sets  
- Computes performance metrics & confidence intervals  
- Generates final tables and visualization outputs  

---

## 🧾 Notes
This repository provides a **reproducible implementation** of the manuscript:  
**“Interpretable Multi-Modality Consensus QSAR Framework Integrating Machine and Deep Learning for Enhanced Multi-Endpoint Toxicity Assessment.”**

For:
- Endpoint definitions  
- Data curation rules  
- Complete descriptor list (Table S1)  
- Hyperparameter settings (Table S2)  

See the **Supporting Information** section of the manuscript.

---

## 📚 Citation
If you use this repository in your research, please cite the article once published:  
> Citation details will be updated after publication.

---

## 🧠 Acknowledgments
This work is conducted under the **Computational Medicine Lab**, Kumoh National Institute of Technology, Gumi, Republic of Korea.

---.

---

