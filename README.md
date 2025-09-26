
# 🔥 Distributed Wildfire Confidence Prediction using H2O.ai

A **multiclass classification project** leveraging a **2-node distributed H2O cluster** and a **Distributed Random Forest (DRF)** model to predict wildfire confidence levels (`Low`, `Nominal`, `High`) using **NASA VIIRS SNPP 2023 global fire data**.

---

## 📌 Highlights
- Built a **high-accuracy wildfire classification system** using global satellite data  
- Deployed a **Distributed Random Forest (DRF)** model via **H2O.ai**  
- Processed **large-scale datasets** using distributed computing  
- Evaluated performance with metrics: **AUC, Accuracy, F1-score**  
- Scalable solution for **real-world wildfire monitoring**  

---

## 🧾 Project Overview
This project presents a **scalable, distributed ML pipeline** for wildfire prediction.  
It uses **H2O.ai Distributed Random Forest** on **NASA VIIRS SNPP Active Fire Data (2023)** to classify fire confidence levels.

**Key Components**:
- Distributed training on a **2-node H2O cluster**  
- End-to-end pipeline: preprocessing → training → evaluation → predictions  
- Comparison of **AutoML Leaderboard Models (GBM, XGBoost, GLM, DRF, Ensembles)**  
- Manual **Random Forest** for interpretability  

---

## 🎯 Motivation
Wildfires are increasing due to climate change, making **early detection & classification** vital for disaster management.  

Challenges:  
- Huge datasets (global, daily fire events)  
- Need for **scalable ML solutions**  

Why H2O.ai?  
- Distributed computing across nodes  
- Built-in AutoML & explainability  
- Handles massive structured datasets efficiently  

---

## 📂 Repository Structure
 wildfire_pred_h2o/
├── Final_Distributed_ML_using_H2O_Framework.ipynb # Main notebook
├── Project_Report.pdf # Detailed report
├── flatfile.txt # H2O node list for cluster
├── requirements.txt # Python dependencies
├── csv_merge.py # CSV merge utility
├── AutoML.txt # AutoML notes
├── Setup1.png, Setup2.png # Cluster setup screenshots
└── README.md # This file


---

## 📦 Dataset
- **Source:** [NASA VIIRS SNPP Active Fire/Hotspot Data (375m, 2023)](https://firms.modaps.eosdis.nasa.gov/download/)  
- **Coverage:** Global, Jan–Dec 2023  
- **Resolution:** 375m, WGS84 projection  
- **Format:** CSV  

**Features Used:** latitude, longitude, brightness, scan, track, date/time, satellite, confidence, FRP, day/night  

⚠️ Dataset not included (too large). Download directly from NASA FIRMS.

---

## 🛠 Preprocessing
- **Merge CSVs** (country-wise → global dataset) using `csv_merge.py`  
- **Feature engineering & cleaning** (categorical encoding, null handling)  
- **Split into train/validation/test** (70/15/15)  

---

## 🤖 Model Training
### 1. AutoML (Distributed)
- Framework: **H2O AutoML**  
- Models trained: GBM, DRF, XGBoost, GLM, Deep Learning, Stacked Ensembles  
- Evaluated with leaderboard (AUC, LogLoss, variable importance)  

### 2. Manual DRF (Baseline)
```python
from h2o.estimators.random_forest import H2ORandomForestEstimator

rf_model = H2ORandomForestEstimator(ntrees=30, max_depth=20, seed=1234)
rf_model.train(x=features, y="confidence", training_frame=train, validation_frame=valid)


