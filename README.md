# student-performance-prediction
A Machine Learning model predicting exam scores using study hours and student habits.

# 🎓 Student Exam Score Prediction

This project implements a **Machine Learning (Linear Regression)** model to predict student exam scores based on their study habits, attendance, and sleep quality.

## 🚀 Project Overview
The goal is to analyze how different factors contribute to academic performance and build a prediction system that estimates a student's final score.

## 🛠️ Technologies & Tools
* **Python** (Pandas, NumPy)
* **Scikit-Learn** (Linear Regression, LabelEncoder, train_test_split)
* **Seaborn & Matplotlib** (Data Visualization & Heatmaps)

## 📊 Key Analysis & Methodology
1.  **Data Preprocessing:** * Checked for missing values and duplicates.
    * Applied **Label Encoding** to categorical features (e.g., `sleep_quality`, `study_method`) to convert them into numeric format for the model.
2.  **Correlation Analysis:** * Identified that **Study Hours (0.72)** and **Class Attendance (0.31)** have the highest correlation with exam scores.
3.  **Model Training:** * Split the dataset into Training (80%) and Testing (20%) sets.
    * Trained a **Linear Regression** model.
4.  **Engineering Logic (Post-Processing):** * Implemented a **Prediction Function** with error handling for user inputs.
    * **Clipping Logic:** Added a logic layer to restrict predictions between **0 and 100**, preventing unrealistic scores (e.g., 139/100).

## 📈 Results
* **R² Score:** ~0.66 (The model explains 66% of the variance in exam scores).
* **Insight:** Study hours are the most significant predictor of success.

## 🚀 Model Improvements (v2.0)

After the initial deployment, I analyzed the feature importance and realized that the `course` (education level) variable had a hierarchical nature (e.g., *Masters > Bachelors > High School*).

To improve the model, I applied the following techniques:
1.  **Feature Engineering (Ordinal Encoding):** Instead of standard label encoding, I mapped the `course` variable based on educational hierarchy (Diploma < BA/BBA < B.Tech).
2.  **Feature Scaling (Standardization):** Applied `StandardScaler` to normalize the range of independent variables.

### 📊 Results Comparison
| Metric | Initial Model (v1.0) | Optimized Model (v2.0) |
| :--- | :---: | :---: |
| **R² Score** | ~66.00% | **71.94%** |
| **Method** | Linear Regression (Raw) | Linear Regression (Scaled + Ordinal) |

*This update resulted in a **~9% performance boost**, proving that domain knowledge (ranking education levels) significantly impacts prediction accuracy.*

---
*Developed by Ergün Üngör*
