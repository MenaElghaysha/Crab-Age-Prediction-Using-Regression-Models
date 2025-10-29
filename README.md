# 🦀 Crab Age Prediction Using Regression Models

## 📘 Overview

This project predicts the **age of crabs** using their physical measurements such as length, weight, diameter, and shell weight.
The primary goal is to explore multiple regression algorithms, engineer meaningful features, and identify the model that best estimates crab age.

The project demonstrates:

* End-to-end machine learning workflow
* Advanced feature engineering
* Multiple pipeline architectures
* Model comparison and fine-tuning with **GridSearchCV**
* Evaluation using **Root Mean Squared Error (RMSE)**

---

## 📊 Dataset

* **Source:** [Crab Age Prediction Dataset (Kaggle)](https://www.kaggle.com/)
* **Description:** The dataset includes various biological and physical measurements of crabs.
  Each record corresponds to a crab, and the target variable is its **age** (in years).

**Features:**

| Feature         | Description                                                   |
| --------------- | ------------------------------------------------------------- |
| Sex             | Male, Female, or Infant                                       |
| Length          | Largest distance from the front to the back of the shell (mm) |
| Diameter        | Widest point perpendicular to the length (mm)                 |
| Height          | Height of the crab (mm)                                       |
| Weight          | Whole weight of the crab (g)                                  |
| Shucked Weight  | Weight of meat only (g)                                       |
| Viscera Weight  | Weight of gut content (g)                                     |
| Shell Weight    | Weight of shell after being dried (g)                         |
| **Target:** Age | Estimated age of the crab (years)                             |

---

## ⚙️ Project Workflow

### 1. Data Preprocessing

* Handled missing values and outliers
* Encoded categorical variables (Sex) using **OneHotEncoder**
* Scaled numerical features with multiple strategies:

  * `StandardScaler`
  * `RobustScaler`
  * `MinMaxScaler`
* Built **three custom preprocessing pipelines** to test scaling and imputation variations

### 2. Feature Engineering

Custom features were added to enrich the dataset:

* **Volume** = `Length × Weight × Height`
* **Shell Weight Ratio** = `Shell Weight / Weight`

### 3. Model Training

Trained and compared multiple regression algorithms:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor
* **LightGBM Regressor (Best Performer)**

### 4. Model Fine-Tuning

Fine-tuned the **LightGBM** model using `GridSearchCV` with parameters:


### 5. Evaluation

Used **Root Mean Squared Error (RMSE)** to evaluate model performance on training, validation, and test sets.

---

## 📈 Results

The **LightGBM** model provided the best generalization with minimal overfitting, making it the final chosen model.

|Metric	| Train RMSE	| Validation RMSE	|Test RMSE|
| ------|---------------|-------------------|---------|
|Value	|1.956	|2.061	|2.417  |




These results show that the model generalizes well across unseen data, with only a small increase in error from validation to test sets.

---

## 📊 Visualizations

* **Feature Correlation Heatmap**
* **Distribution of Numerical Features**
* **Outlier Detection (Boxplots)**
* **Feature Importance (LightGBM)**

---

## 🧠 Tech Stack

* **Python 3.10+**
* **pandas**, **numpy**, **matplotlib**, **seaborn**
* **scikit-learn**
* **XGBoost**
* **LightGBM**



---

## 🚀 How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/MenaElghaysha/Crab-Age-Prediction-Using-Regression-Models.git
   cd crab-age-prediction
   ```

2. Open the notebook:

   ```bash
   jupyter notebook "Crab Age Prediction.ipynb"
   ```

3. Run all cells to reproduce the results.

---

## 🧩 Future Improvements

* Add more biological features for better accuracy
* Implement **cross-validation visualization**
* Experiment with **deep learning regression**
* Automate pipeline tuning with **Optuna** or **Bayesian Optimization**

---

## 👤 Author

**Mena H. Elghaysha**
Machine Learning Engineer & Data Analyst

---

## 📜 License

This project is licensed under the **MIT License** — feel free to use and modify it.

