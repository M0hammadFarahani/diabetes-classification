# 🩺 Multiclass Diabetes Classification

## 📌 Overview
This project aims to **predict the type of diabetes (Type 1, Type 2, or Non-diabetic)** based on patients' medical attributes.  
The dataset used is a cleaned and balanced subset of the *Multiclass Diabetes Dataset* from Kaggle/Mendeley, which has been processed to remove duplicates and partially balance the classes.

---

## 📊 Dataset
- **Source**: [Multiclass Diabetes Dataset – Kaggle](https://www.kaggle.com/datasets/yasserhessein/multiclass-diabetes-dataset) / [Mendeley Data](https://data.mendeley.com/datasets/jpp8bsjgrm)
- **Original records**: 1,000  
- **After removing duplicates**: 826 unique samples  
  - Diabetic: 690  
  - Non-diabetic: 96  
  - Pre-diabetic: 40  
- **Final subset used in this project**:
  - Diabetic: 128  
  - Non-diabetic: 96  
  - Pre-diabetic: 40  

**Target variable (`Class`)**:  
- `0` → Non-diabetic  
- `1` → Pre-diabetic (Type 1)  
- `2` → Diabetic (Type 2)

---

## 🛠 Workflow
1. **Exploratory Data Analysis (EDA)**  
   - Dataset shape, data types, summary statistics  
   - Class distribution visualization  
   - Correlation heatmap for feature relationships  
2. **Preprocessing**  
   - Splitting features and target column  
   - Train-test split with stratification  
   - Feature scaling using `StandardScaler`  
3. **Handling Class Imbalance**  
   - Applied **SMOTE** with `sampling_strategy={1: 96}` to oversample Class 1 to match Class 0 size  
4. **Model Training & Evaluation**  
   - Models used:
     - Logistic Regression
     - RandomForestClassifier
     - XGBClassifier
     - K-Nearest Neighbors (KNN)
   - Evaluation metrics:
     - Accuracy
     - Precision, Recall, F1-score
     - Confusion Matrix
   - Accuracy comparison plotted for all models

---

## 📈 Results

| Model                  | Accuracy | Key Notes |
|------------------------|----------|-----------|
| Logistic Regression    | 0.89     | Class 1 performance improved after SMOTE |
| RandomForestClassifier | **0.98** | Best overall performance, high precision & recall for all classes |
| XGBClassifier          | 0.96     | Close to RandomForest |
| KNN                    | ~0.79    | Lower performance compared to others |

**Main observations**:
- SMOTE improved minority class (Class 1) performance significantly.
- RandomForestClassifier achieved the best accuracy (98%) and overall metrics.

