# Churn Prediction App for ISP

This project is a **Streamlit web application** that predicts whether a customer will churn (leave) an Internet Service Provider (ISP) based on their demographic and account information. The prediction is powered by a machine learning model trained using a Support Vector Machine (SVM) classifier.

---

## Features

- **Interactive web interface** for entering customer details.
- Real-time churn prediction using a trained SVM model.
- Utilizes pre-trained scaler and model for consistent and accurate predictions.

---

## Technologies Used

- **Python 3**
- **Streamlit** (for the web application)
- **scikit-learn** (for model training and preprocessing, including SVM)
- **joblib** (for model and scaler serialization)
- **NumPy** (for numerical operations)
- **Dataset**: https://www.kaggle.com/datasets/abdullah0a/telecom-customer-churn-insights-for-analysis

---

## Machine Learning Model

- **Algorithm:** Support Vector Machine (SVM) from scikit-learn.
- **Features Used:**  
  - `Age`
  - `Gender` (encoded: 1 = Female, 0 = Male)
  - `Tenure`
  - `MonthlyCharges`
- **Preprocessing:**  
  - Features are standardized using a `StandardScaler` (saved as `scaler.pkl`).
  - The SVM model is trained and saved as `model.pkl`.
- **Prediction Output:**  
  - `1` = Yes (Customer will churn)
  - `0` = No (Customer will not churn)

---

## Local Setup Instructions

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd churn_prediction
```

### 2. (Recommended) Create and Activate a Virtual Environment

```bash
python -m venv .venv
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```
If `requirements.txt` is not available, install manually:
```bash
pip install streamlit scikit-learn joblib numpy
```

### 4. Ensure the Following Files Are Present

- `app.py` (the Streamlit application)
- `scaler.pkl` (the pre-trained scaler)
- `model.pkl` (the trained SVM model)
- `.streamlit/config.toml` (optional, for theme settings)

### 5. Run the Streamlit App

```bash
streamlit run app.py
```

### 6. Access the App

- Open the provided local URL (e.g., `http://localhost:8501`) in your browser.
- To access from another device on the same network, use the network URL shown in the terminal (e.g., `http://192.168.1.11:8501`).

---

## Notes

- Input features must be provided in the order: `['Age', 'Gender', 'Tenure', 'MonthlyCharges']`.
- The scaler and model must match the features and preprocessing used during training.
- For best results, use the same Python environment as used for model training.

