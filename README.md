Telecom Company - Customer Churn Prediction (Imbalanced Classification)

## 📌 Overview
In this project, I developed a **binary classification model** to analyze clients’ past behavior and contract termination data to predict whether a customer is likely to leave the company.

---

## ⚙️ Preprocessing
- Performed **descriptive statistics** to explore the data and identify missing values  
- **Standardized column names** to lowercase for consistency  
- Converted data types:  
  - `begin_date` and `end_date` → datetime  
  - `total_charges` → numeric  
- **Created the target variable `churn`**:  
  - `1` if `end_date` is not 'No'  
  - `0` if `end_date` is 'No'  
- **Handled missing values**:  
  - `total_charges` missing → filled with `monthly_charges`  
- **Created derived features**:  
  - `tenure_days` = difference between `begin_date` and `end_date` (in days)  
- **One-Hot Encoded** categorical features  
- Checked for **duplicates** to prevent bias  

---

## 📈 Evaluation Metrics
- **ROC-AUC** (primary metric)
- Balanced Accuracy

---

## 🛠️ Tech Stack
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  


---

## 🔍 Exploratory Data Analysis (EDA)
- No significant **outliers** were observed; data kept as is  
- **Month-to-month contracts** are the most common among customers  
- `monthly_charges` cluster around **$20**, suggesting a common plan  
- Many customers with `total_charges < $100` — likely new or short-tenure customers  

---

## ⚖️ Model Preparation
- Target classes are **imbalanced**: >2× more customers stayed than left  
- Strategies to address imbalance:  
  - `stratify` during **train-test split**  
  - **Class Weight Adjustment**  
  - **Upsampling**  

---

## 🤖 Models Used
- Decision Tree  
- Random Forest  
- Logistic Regression  

Each model was:
- Trained with **default parameters**
- Improved using **imbalance handling techniques**
- Optimized via **hyperparameter tuning**

---

## 🤖 Hyperparameter Tuning
- Algorithms tuned: **Random Forest, XGBoost, LightGBM**  
- For top models, **thresholds were looped over** to maximize **Balanced Accuracy**, improving performance on both classes  

---

## 🏆 Best Model
**XGBoost (Balanced, Tuned, Threshold Optimized)**

### 🔹 Training Performance
- **ROC-AUC:** 0.92  
- **Balanced Accuracy:** 0.84  

### 🔹 Test Set Performance
- **ROC-AUC:** 0.90  
- **Balanced Accuracy:** 0.80  

### 🔹 Full Dataset Performance (Retrained)
- **ROC-AUC:** 0.92  
- **Balanced Accuracy:** 0.83  

✅ Confirms strong generalization and effective detection of churned and non-churned customers  

---

## 📊 Insights & Visualization
- ROC curves and threshold analysis show the **model’s strong discriminative power**  
- Adjusting **decision thresholds** improves **Balanced Accuracy**  
- Next step: visualizing **ROC curve** for detailed model performance analysis  

---

## 📎 How to Run
```bash
git clone https://github.com/yalchinalasgar/telecom-churn-prediction-ml.git
cd telecom-churn-prediction-ml
pip install -r requirements.txt


---

## 👤 Author
**Yalchin Alasgarli**  
- GitHub: https://github.com/yalchinalasgar  
- LinkedIn: https://www.linkedin.com/in/yalchin-alasgarli/

---

## ⭐️ If you found this project useful, feel free to star the repo!
