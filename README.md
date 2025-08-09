#  Breast Cancer Classification

This project predicts whether a breast tumor is **Benign (B)** or **Malignant (M)** using multiple machine learning models.  
It includes **Exploratory Data Analysis (EDA)**, model training, performance evaluation, and handling of mild class imbalance.

---

##  Dataset
The dataset used is the Breast Cancer Wisconsin (Diagnostic) dataset, and each of these features comes from a digitized image of a breast mass taken from a fine needle aspirate (FNA).
The features describe the shape, texture, and other properties of the cell nuclei found in the image.
They are grouped into three main measurement types: mean, standard error (se), and worst (largest value).

** Top 15 Features:**

| Feature | Description |
|---------|-------------|
| **diagnosis** | Target variable — `M` = Malignant, `B` = Benign (in ML models, usually encoded as `1` and `0`). |
| **concave points_worst** | Largest number of concave points (indentations) observed on the tumor boundary among all cells in the image. Higher values indicate more irregular shapes. |
| **perimeter_worst** | Largest perimeter measured for the tumor across all cells — linked to tumor size. |
| **concave points_mean** | Average number of concave points on the tumor boundary — measures irregularity in contour. |
| **radius_worst** | Largest radius among all cell nuclei — calculated as average distance from center to boundary. |
| **perimeter_mean** | Average length of the tumor boundary. |
| **area_worst** | Largest area measured among the cell nuclei — correlated with tumor mass size. |
| **radius_mean** | Average radius from center to perimeter across all nuclei. |
| **area_mean** | Average area of the tumor. |
| **concavity_mean** | Average severity of concave portions of the contour — higher means deeper indentations. |
| **concavity_worst** | Largest severity of concave portions among all cells — indicates most extreme irregularity. |
| **compactness_mean** | Average compactness = (perimeter² / area) - 1.0 — measures how closely packed the shape is. |
| **compactness_worst** | Worst (largest) compactness value observed. |
| **radius_se** | Standard error of the radius measurement — shows variation in radii between cells. |
| **perimeter_se** | Standard error of the perimeter measurement — shows variation in perimeter lengths between cells. |

---

##  Exploratory Data Analysis (EDA)
- Distribution plots for categorical variables
- Correlation heatmap for top correlated features
  
---

##  Machine Learning Models Used
- SVM
- Random Forest 
- Logistic Regression 

---

##  Steps Implemented
1. **Data Preprocessing**
   - Handling missing values
   - Encoding categorical variables
   - Feature scaling
2. **Feature Engneering**
   - Select Top 15 highly corelated features
   - Balance Target Feature
2. **Model Training & Evaluation**
   - Train-test split
   - Evaluation using Accuracy, Precision, Recall, F1-score, and ROC-AUC
5. **Model Comparison**
   - Selected best model based on performance metrics

##  Model Comparison
| Model           | Class Weight | ROC-AUC | Accuracy |
|-----------------|-------------|---------|----------|
| Logistic Regression | Balanced | 0.995 | 0.972|
| Linear SVM      | Balanced | 0.991	 | 0.958 |
| RBF SVM         | Balanced | 0.997 | 0.993 |
| Random Forest   | Balanced | 0.998 | 0.965 |

---

##  Tech Stack
- **Language:** Python 
- **Libraries:** pandas, matplotlib, seaborn, scikit-learn, imbalanced-learn

---
###  Result
**RBF SVM** achieved the highest accuracy of **99.3%** on the test set,  
making it the best choice for this dataset.


**Confusion Matrix (Best Model — RBF SVM):**


|                 | **Predicted Positive** | **Predicted Negative** |
|-----------------|------------------------|------------------------|
| **Actual Positive** | 52                   | 1                      |
| **Actual Negative** | 0                    | 90                     |

