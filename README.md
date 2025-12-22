# Phishing Detection Project

This project builds machine learning models to detect phishing URLs using a balanced Kaggle dataset of 235,795 URLs with 56 features. The 50/50 split between phishing and legitimate links ensures an unbiased evaluation. This dataset is ideal for rapid experimentation and aligns with our cybersecurity focus.

## 🚀 Key Improvements & Data Integrity
Initially, the models achieved a suspicious **100% accuracy**. After a deep dive into **Feature Importance**, we identified and removed **Data Leakage** caused by structural features (e.g., `LineOfCode`, `NoOfJS`, `NoOfExternalRef`, `IsHTTPS`) that were pre-calculated and highly correlated with the labels in this specific dataset.

By excluding these features, we forced the models to learn more generalizable phishing patterns, resulting in realistic and credible performance metrics.

## 📊 Model Performance (Final Results)
After fixing the leakage, we compared three different approaches on a test set of **70,739 samples**. The results show a logical technical hierarchy where the Random Forest performs best:

| Model | Accuracy | ROC-AUC | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Random Forest** | **0.9928** | **0.9996** | **0.9907** | **0.9967** | **0.9937** |
| **Decision Tree** | 0.9847 | 0.9960 | 0.9857 | 0.9876 | 0.9866 |
| **Logistic Regression** | 0.9780 | 0.9974 | 0.9797 | 0.9819 | 0.9808 |



## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** Pandas, Scikit-learn, Matplotlib, NumPy
* **Data Handling:** Missing value imputation (median) and feature scaling for Logistic Regression.

## 📈 Visual Comparison
The project includes a comprehensive comparison using Bar Plots and Radar Charts to visualize the trade-offs between accuracy, precision, and recall across all models.
