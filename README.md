## Credit_Score_Processing
### **Credit Score Prediction — End‑to‑End Machine Learning Pipeline**

A complete and well‑structured machine learning workflow for credit‑risk modeling, including preprocessing, visualization, and hybrid feature selection using both linear and non‑linear techniques.

### **Project Overview**

This project builds a robust ML pipeline to predict customer credit outcomes. It walks through:
- Data loading and cleaning
- Handling missing values
- Scaling and encoding
- Exploratory visualizations
- Multiple feature‑selection strategies
- A final ensemble‑based feature selection approach
  
The goal is to create a reliable, interpretable, and production‑ready workflow for credit‑risk analysis.

### **1. Data Loading & Initial Preparation**
   
The dataset is imported and inspected to ensure correct loading. Irrelevant identifiers such as customer IDs and surnames are removed because they do not contribute to predictive modeling.

### **2. Data Cleaning & Preprocessing**
   
**Handling Missing Values**
- Numerical columns are imputed using the median, which is robust to outliers.
- Categorical columns are imputed using the mode, ensuring consistency in category representation.
  
**Scaling Numerical Features**

A Robust Scaler is applied to numerical variables to reduce the influence of outliers while preserving feature distribution.

**Encoding Categorical Variables**

Categorical features such as geography and gender are transformed using one‑hot encoding, enabling them to be used effectively in machine learning models.

### **3. Exploratory Data Visualization**
   
Several visual techniques are used to understand relationships and patterns:

**Clustered Heatmap**

Shows correlations between all features using hierarchical clustering to reveal natural groupings.

**Parallel Coordinates Plot**

An interactive visualization that highlights how feature values differ between customers who exited and those who did not.

**Radial (Spider/Web) Plot**

Displays the mean value of each feature, offering a holistic view of feature distributions.

### **4. Train–Test Split**
   
The dataset is split into training and testing sets using a stratified approach to preserve the distribution of the target variable. This ensures fair evaluation and prevents bias.

### **5. Feature Selection Techniques**
   
Multiple feature‑selection methods are applied to understand which features contribute most to predicting customer exit behavior.

**A. Principal Component Analysis (PCA)**

PCA is used to explore dimensionality reduction. Although it identifies components explaining most variance, it is not suitable for interpretability because principal components lose the identity of original features. Therefore, PCA is not used for final feature selection.

**B. Lasso Regression (L1 Regularization)**

Lasso applies strong penalization and selects only a small subset of features.
However, it tends to be overly restrictive and biased, especially when relationships are non‑linear.

**C. Ridge Regression (L2 Regularization)**

Ridge keeps all features but shrinks coefficients based on importance.
It selects a broader set of meaningful features compared to Lasso, reflecting its more balanced nature.

**D. Random Forest (Non‑Linear Feature Importance)**

A tree‑based model is used to capture non‑linear relationships.
Feature importance scores are computed, and features above the mean importance threshold are selected.
This method provides a more realistic view of feature influence in complex datasets.

### **6. Ensemble Feature Selection**

To achieve both robustness and accuracy, the project compares feature sets from:
- Lasso (L1)
- Ridge (L2)
- Random Forest (non‑linear)
  
A Venn diagram visualizes the overlap.

### **Final Selection Strategy**

The final feature set is chosen by taking the intersection of Ridge and Random Forest, combining:
- Stability from linear models
- Flexibility from non‑linear models
  
This hybrid approach ensures the selected features are both statistically reliable and contextually meaningful.
![Common Features selected by both Ridge and Random Forest](assets/Common%20Features%20selected%20by%20both%20Ridge%20and%20Random%20Forest.png)

### **Conclusion**
This project demonstrates a complete, production‑ready ML pipeline for credit‑risk modeling. It includes:
- Clean preprocessing
- Strong visual diagnostics
- Multiple feature‑selection strategies
- A hybrid ensemble approach for final feature selection
  
The resulting feature set is interpretable, stable, and optimized for downstream modeling, making this workflow suitable for real‑world financial applications.
