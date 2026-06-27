# ❤️ Heart Disease Prediction

A machine learning project that predicts heart disease risk based on clinical parameters, with an interactive **Streamlit** web application for real-time inference.

---

## 🚀 Demo

> Run the app locally and enter patient vitals to get an instant **High Risk / Low Risk** prediction powered by a K-Nearest Neighbors classifier.

---

## 📁 Project Structure

```
heart-disease-prediction/
├── heart_disease_prediction.ipynb   # EDA, preprocessing, model training & evaluation
├── app.py                           # Streamlit web application
├── KNN_heart.pkl                    # Trained KNN model (generated after running notebook)
├── scaler.pkl                       # Fitted StandardScaler (generated after running notebook)
├── columns.pkl                      # Expected feature columns (generated after running notebook)
├── heart.csv                        # Dataset (add your own copy)
├── requirements.txt
└── README.md
```

---

## 🧠 Models Evaluated

| Model               | Description                            |
|---------------------|----------------------------------------|
| Logistic Regression | Baseline linear classifier             |
| **KNN**             | ✅ Selected — best F1 score            |
| Naive Bayes         | Probabilistic classifier               |
| Decision Tree       | Tree-based interpretable model         |
| SVM (RBF Kernel)    | Support vector machine with RBF kernel |

The **KNN classifier** was selected for deployment based on accuracy and F1 score on the held-out test set.

---

## 📊 Dataset

**Source:** [Heart Failure Prediction Dataset – Kaggle](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)

| Feature           | Description                              |
|-------------------|------------------------------------------|
| Age               | Patient age in years                     |
| Sex               | M / F                                    |
| ChestPainType     | ATA / NAP / TA / ASY                     |
| RestingBP         | Resting blood pressure (mm Hg)           |
| Cholesterol       | Serum cholesterol (mg/dL)                |
| FastingBS         | Fasting blood sugar > 120 mg/dL (0 / 1) |
| RestingECG        | Normal / ST / LVH                        |
| MaxHR             | Maximum heart rate achieved              |
| ExerciseAngina    | Exercise-induced angina (Y / N)          |
| Oldpeak           | ST depression induced by exercise        |
| ST_Slope          | Slope of peak exercise ST segment        |
| **HeartDisease**  | **Target — 1: Disease, 0: Normal**       |

**Preprocessing steps:**
- Zero values in `Cholesterol` and `RestingBP` replaced with column mean
- One-hot encoding for all categorical features (`drop_first=True`)
- Features scaled with `StandardScaler`
- 80/20 stratified train-test split

---

## ⚙️ Installation

```bash
git clone https://github.com/<your-username>/heart-disease-prediction.git
cd heart-disease-prediction
pip install -r requirements.txt
```

---

## 🏃 Usage

### 1. Train the model

Open and run all cells in `heart_disease_prediction.ipynb`.  
This generates `KNN_heart.pkl`, `scaler.pkl`, and `columns.pkl`.

> Make sure `heart.csv` is in the project root before running.

### 2. Launch the Streamlit app

```bash
streamlit run app.py
```

Open the URL shown in your terminal (typically `http://localhost:8501`).

---

## 🖥️ App Features

- Sliders and dropdowns for all 11 clinical input features
- One-click **Predict** button
- Color-coded result: 🔴 High Risk / 🟢 Low Risk

---

## 🛠️ Tech Stack

| Layer       | Tools                                          |
|-------------|------------------------------------------------|
| Language    | Python 3.x                                     |
| ML          | scikit-learn (KNN, Logistic Regression, SVM, etc.) |
| EDA         | Pandas, NumPy, Matplotlib, Seaborn             |
| App         | Streamlit                                      |
| Persistence | Joblib                                         |

---


