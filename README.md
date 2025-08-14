# 📡 Machine Learning-Based LTE Network Optimisation
This project applies machine learning to analyse LTE radio coverage data, uncover patterns in signal quality, and build predictive models for network performance optimisation.
Using clustering, classification, and evolutionary optimisation techniques, the project transforms raw LTE measurements into actionable insights for improving Quality of Service (QoS) and user experience.

## 📋 Project Overview
### Objectives
Analyse large-scale LTE measurement data to identify patterns in signal quality & mobility scenarios
Build predictive models to classify signal conditions and usage scenarios
Apply Genetic Algorithms for hyperparameter tuning to improve model performance
Extract key predictors influencing LTE performance for actionable network optimisation strategies

## 🛠 Tech Stack
**Language:**  
- Python 3.12  

**Libraries & Frameworks:**  
- **Data Processing:** `pandas`, `numpy`  
- **Visualisation:** `matplotlib`, `seaborn`  
- **Machine Learning:** `scikit-learn`, `xgboost`  
- **Optimisation:** `sklearn-genetic`, `DEAP`  
- **Utilities:** `kneed`, `scipy`  


## 📂 Dataset
**Source:** - 4G Passive Measurement dataset

**Article:** Kousias, K., Rajiullah, M., Caso, G., Ali, U., Alay, O., Brunstrom, A., De Nardis, L., Neri, M., and Di Benedetto, M.G., 2022. A large-scale dataset of 4G, NB-IoT, and 5G non-standalone network measurements. IEEE Dataport. Available at: https://dx.doi.org/10.21227/7a8s-nt68 [Accessed 14 May. 2025].

**Size:** 527,540 records × 27 features
### Features:
**Numerical:** RSRP, RSRQ, SINR, Speed, Distance, Altitude, Frequency, Band, etc.
**Categorical:** Scenario (Indoor Static, Outdoor Walking, Outdoor Driving), MNC, Campaign, etc.
####  Target Variables:
**Binary:** Signal (RSRP > -100 dBm) vs No Signal
**Multi-class:** Mobility scenarios (Indoor Static, Outdoor Walking, Outdoor Driving)

# 🔍 Workflow

## 1. Data Preprocessing & EDA
- Removed duplicates & handled missing values (interpolation, mean imputation, forward fill)  
- Outlier detection using **IQR** and **Z-score**  
- Encoding: One-hot & Label Encoding for categorical variables  
- Scaling: **Z-score normalisation** for numerical features  
- Exploratory visualisation (correlation heatmaps, KDE plots, boxplots, scenario-based distributions)  

## 2. Clustering Analysis
- **K-Means**: Determined optimal clusters using the **Elbow Method** & **Genetic Algorithms** (Silhouette score)  
- **DBSCAN**: Parameter tuning via k-distance plot for noise detection & irregular cluster shapes  
- **Insights**: 4 distinct user profiles — from strong indoor signals to weak edge-of-coverage zones  

## 3. Classification Models
- **Binary Classification**: Logistic Regression, Random Forest  
- **Multi-class Classification**: Random Forest, XGBoost  
- **Evaluation**: Accuracy, Precision, Recall, F1-score, ROC-AUC  
- Feature importance analysis to identify top predictors  

## 4. Hyperparameter Optimisation
- **Genetic Algorithms** used for Random Forest tuning  
- Parameters tuned: `n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf`, `criterion`  
- Performance gains across all metrics  

---

# 📊 Results

| Task                    | Best Model         | Accuracy | Key Notes |
|------------------------|-------------------|----------|-----------|
| Binary Classification  | Random Forest     | ~97%     | High precision & recall; key predictors: Power, SINR, RSRQ |
| Multi-class Classification | XGBoost        | ~100%    | Excellent scenario prediction accuracy |
| Clustering             | K-Means (k=4)     | Silhouette ~0.49 | Clear separation of mobility & signal profiles |
| GA Optimisation        | Random Forest     | +0.15% Accuracy | Reduced FP & FN; improved balance |

---

# 📈 Visual Highlights
- **Correlation Heatmaps**: Identified multicollinearity between RSRP & Power  
- **Clustering Plots**: Visualised user groups based on signal strength & mobility  
- **ROC Curves**: High AUC scores for classification models  
- **Feature Importance**: Power, SINR, RSRQ consistently top-ranked  

---

# 📌 Key Insights
- Machine learning can accurately classify LTE signal conditions & mobility scenarios  
- Combining clustering with predictive modelling enables more targeted network optimisation  
- Genetic Algorithms are effective for fine-tuning complex models without exhaustive grid search  

---

# 📬 Contact
**Author:** Akinlolu Adepoju  
📧 Email: [adepojuakinloluferanmi@gmail.com](mailto:adepojuakinloluferanmi@gmail.com)  
💼 LinkedIn: [Akinlolu Adepoju](https://www.linkedin.com/in/akinlolu-adepoju-8b41961aa/)  
