
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
