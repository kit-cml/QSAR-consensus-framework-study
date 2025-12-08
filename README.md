# Consensus-Based QSAR Framework for Enhanced Prediction of Comprehensive Multi-Endpoint Chemical Toxicities

**FAUZAN SYARIF NURSYAFI¹, MUHAMMAD ADNAN PRAMUDITO², YUNENDAH NUR FUADAH³*, and KI MOO LIM¹,⁴,⁵***

¹Computational Medicine Lab, Department of Medical IT Convergence Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
²Computational Medicine Lab, Department of IT Convergence Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
³Telecommunication Engineering Study Program, School of Electrical Engineering, Telkom University Main Campus, Bandung, Indonesia  
⁴Computational Medicine Lab, Department of Biomedical Engineering, Kumoh National Institute of Technology, Gumi, 39177, Republic of Korea  
⁵Meta Heart Co., Ltd, Gumi, 39253, Republic of Korea  

*Corresponding authors: kmlim@kumoh.ac.kr, yunendah@telkomuniversity.ac.id*

---

## Overview
This repository contains the code for developing and evaluating QSAR (Quantitative Structure–Activity Relationship) models for **multi-endpoint chemical toxicity prediction**. The models employ a **consensus-based approach** integrating:

- Multiple molecular fingerprints: **Morgan, MACCS, APF**  
- Physicochemical descriptors (RDKIT + CDK)  
- Machine learning algorithms: **Random Forest (RF), XGBoost (XGB), Support Vector Machine (SVM)**  

Cross-validation ensures robust and reliable model performance.

The datasets cover **9 toxicity endpoints**:

1. Skin Sensitization  
2. Respiratory Toxicity  
3. AMES Mutagenicity  
4. Drug-Induced Liver Injury (DILI)  
5. Hepatotoxicity  
6. Developmental Toxicity  
7. Cardiotoxicity  
8. Carcinogenicity  
9. FDA Maximum Daily Dose (FDA MDD)  

Total compounds: **31,723**, with **seven endpoints retaining their original train/test splits** and **two endpoints divided via stratified random split**.

---

## Features
- Data preprocessing and descriptor calculation  
- Model training using both fingerprint and physicochemical features  
- Cross-validation with **original and stratified random splits**  
- Evaluation of both individual and consensus models  
- Ensures reproducibility with fixed package versions  

---

## Dependencies
- Python 3.x  
- RDKit (v2025.3.2)  
- CDK-pywrapper (v0.1.1)  
- TensorFlow (v2.19.0)  
- scikit-learn (v1.6.1)  
- NumPy (v2.1.3)  
- Pandas (v2.2.3)  
- Additional: install-jdk (v0.3.0), bounded-pool-executor (v0.0.3)  

---

## Usage

### 1. Compute Descriptors
Use `Descriptor Computation_Preprosesing data.ipynb` to calculate molecular fingerprints and physicochemical descriptors for your dataset.

### 2. Train Models
- `Training_ML_Fingerprint_10foldCrossvalidation.ipynb` for fingerprint-based models  
- `Training_ML_PhysicochemicalProperties_10foldCrossvalidation.ipynb` for physicochemical descriptor-based models  

### 3. Evaluate Models
- `Performance_Model_Evaluation.ipynb` to perform consensus evaluation and generate metrics for all models.

---

## Citation
If you use this repository in your research, please cite our work. 
