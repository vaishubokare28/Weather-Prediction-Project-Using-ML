# 🌧️ Weather Prediction using Machine Learning (Rainfall Forecast)

## 📚 Project Description

### 🎯 Objective

The objective of this project is to build a **supervised machine learning model** that predicts **whether it will rain or not** based on historical weather data. Accurate rainfall prediction is critical for agriculture, disaster management, transportation, and daily life. This model aims to classify rainfall occurrence using various meteorological parameters such as temperature, humidity, wind, and pressure.

---

## 🧠 Approach

The overall approach to solving this problem is structured in the following phases:

1. **Data Preprocessing**
2. **Exploratory Data Analysis (EDA)**
3. **Feature Engineering & Scaling**
4. **Model Building (Random Forest Classifier)**
5. **Evaluation & Visualization**
6. **Prediction and Interpretation**

---

## ⚙️ Data Preprocessing

1. **Datetime Conversion:**
   `date_time` column is converted to `datetime` format for time-based analysis.

2. **Target Encoding:**
   The `Rainfall` column is converted from categorical (`Yes/No`) to binary format (`1/0`).

3. **Missing Values:**
   Missing values are handled using **forward fill (`ffill`)**, assuming temporal continuity.

4. **Column Dropping:**
   Non-numeric or irrelevant features like `location` are removed to simplify the model.

---

## 📊 Exploratory Data Analysis (EDA)

EDA is used to gain insights into the structure and distribution of data:

* **Rainfall Class Distribution:**
  Checked for class imbalance using a count plot.

* **Temperature vs Humidity:**
  Scatter plot with colors representing rainfall to analyze the relationship between key features.

* **Correlation Heatmap:**
  Visualized how each feature correlates with others, especially with `Rainfall`.

* **Time Series Trend:**
  Monthly average rainfall probability plotted over time to understand seasonal patterns.

---

## 🧪 Feature Selection and Scaling

* The target `Rainfall` and timestamp are removed from feature matrix `X`.
* Features are standardized using **StandardScaler** to ensure uniformity in scale before model training.

---

## 🧠 Model Training

* Model used: **RandomForestClassifier** from scikit-learn
* Parameters: `n_estimators=100`, `random_state=42`
* Split: 80% training and 20% testing

Random Forest is chosen due to its robustness, resistance to overfitting, and ability to handle non-linear relationships and feature importance estimation.

---

## ✅ Model Evaluation

Model performance is assessed using:

* **Accuracy Score**
* **Confusion Matrix**
* **Classification Report**

  * Precision, Recall, F1-Score
* **Feature Importance Plot**

  * Identifies which features most strongly influence the rainfall prediction.

---

## 📈 Visual Outputs

1. **Rainfall Distribution:**
   Visual check for class balance.

2. **Scatter Plot:**
   Shows how humidity and temperature vary with rainfall.

3. **Heatmap:**
   Highlights correlation between variables.

4. **Time Series Trend:**
   Monthly trend of rainfall probability.

5. **Feature Importance:**
   Displays key features contributing to rainfall prediction.

---

## 🧾 Sample Prediction

A test sample is taken from `X_test`, scaled, and passed to the trained model for a single prediction. The output is printed as `1` (Rain) or `0` (No Rain).

---

## 🚀 Key Insights

* Features like **humidity, pressure, wind direction**, and **temperature** are strong indicators of rainfall.
* Random Forest provides reliable performance with minimal tuning.
* The model effectively captures non-linear interactions between features.
* There may be some class imbalance (fewer rain events), which can be improved using techniques like **SMOTE** or **class\_weight balancing** in the future.

---

## 📌 Future Work

* Incorporate **hyperparameter tuning** using `GridSearchCV` or `RandomizedSearchCV`
* Experiment with other models: `XGBoost`, `SVM`, `Logistic Regression`
* Deploy model as an API using Flask or a web interface using Streamlit
* Integrate real-time weather data from an external API for live predictions
* Address class imbalance with advanced resampling techniques

