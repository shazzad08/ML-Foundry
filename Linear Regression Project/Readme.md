# 🚗 Ford Car Price Prediction using Linear Regression

## 📌 Project Overview

This project focuses on predicting the selling price of Ford vehicles using Machine Learning. A **Linear Regression** model was developed and optimized through feature engineering techniques to improve prediction performance.

The project demonstrates a complete machine learning workflow, including:

* Data Cleaning & Exploration
* Exploratory Data Analysis (EDA)
* Feature Encoding
* Feature Scaling
* Feature Engineering
* Model Training
* Model Evaluation
* Performance Improvement

---

## 🎯 Objective

The goal of this project is to build a regression model capable of estimating the market price of a Ford car based on its specifications such as:

* Model
* Year
* Mileage
* Transmission Type
* Fuel Type
* Tax
* MPG
* Engine Size

---

## 📊 Dataset Information

The dataset contains used Ford car listings with the following features:

| Feature      | Description          |
| ------------ | -------------------- |
| model        | Ford car model       |
| year         | Manufacturing year   |
| transmission | Transmission type    |
| mileage      | Total miles driven   |
| fuelType     | Fuel type            |
| tax          | Road tax             |
| mpg          | Fuel economy         |
| engineSize   | Engine size (liters) |
| price        | Target variable      |

---

## 🔍 Exploratory Data Analysis (EDA)

Several visualization techniques were used to understand the data:

* Histogram of car prices
* Correlation Heatmap
* Boxplots for:

  * Year vs Price
  * Engine Size vs Price
  * Transmission vs Price
  * Fuel Type vs Price
  * Model vs Price
* Scatterplots:

  * Mileage vs Price
  * Engine Size vs Price

Key observations:

* Mileage negatively impacts price.
* Newer cars generally have higher prices.
* Engine size has a positive correlation with price.
* Certain models command significantly higher prices.

---

## ⚙️ Data Preprocessing

### 1. Handling Missing Values

The dataset was inspected and found to contain no significant missing values.

### 2. One-Hot Encoding

Categorical variables were converted into numerical form using:

```python
pd.get_dummies()
```

Encoded Features:

* model
* transmission
* fuelType

### 3. Feature Scaling

Numerical features were standardized using:

```python
StandardScaler()
```

Scaled Features:

* year
* mileage
* tax
* mpg
* engineSize

---

## 🤖 Model 1: Baseline Linear Regression

### Workflow

```text
One-Hot Encoding
       ↓
Standard Scaling
       ↓
Train-Test Split
       ↓
Linear Regression
```

### Performance

| Metric   | Score      |
| -------- | ---------- |
| R² Score | 0.84 (84%) |

The baseline model explained approximately **84% of the variance** in vehicle prices.

---

## 🚀 Feature Engineering

To improve model performance, several domain-based features were created.

### Car Age

```python
car_age = 2025 - year
```

Represents the age of the vehicle.

---

### Mileage Per Year

```python
mileage_per_year = mileage / (car_age + 1)
```

Measures average yearly usage.

---

### Tax Per Engine

```python
tax_per_engine = tax / (engineSize + 0.1)
```

Provides a normalized taxation measure.

---

### Fuel Efficiency

```python
fuel_efficiency = mpg / (engineSize + 0.1)
```

Captures fuel economy relative to engine size.

---

### Large Engine Indicator

```python
large_engine = (engineSize > 2).astype(int)
```

Binary feature identifying high-displacement engines.

---

## 🤖 Model 2: Improved Linear Regression

After feature engineering:

* New engineered features were added.
* Year was replaced by car age.
* Data was re-encoded and scaled.
* Model was retrained.

### Performance

| Metric   | Score      |
| -------- | ---------- |
| R² Score | 0.86 (86%) |

---

## 📈 Results

| Model                                | R² Score |
| ------------------------------------ | -------- |
| Baseline Linear Regression           | 84%      |
| Feature Engineered Linear Regression | 86%      |

### Improvement

```text
+2% increase in predictive performance
```

Feature engineering successfully enhanced the model's ability to capture relationships within the data.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook

---

## 📂 Project Structure

```text
Ford-Car-Price-Prediction/
│
├── ford.csv
├── project.ipynb
├── README.md
│
└── assets/
    ├── correlation_heatmap.png
    ├── boxplots.png
    └── model_results.png
```

---

## 📚 Machine Learning Concepts Applied

* Supervised Learning
* Regression Analysis
* Exploratory Data Analysis
* Feature Engineering
* One-Hot Encoding
* Standardization
* Train-Test Split
* Model Evaluation
* R² Score
* RMSE
* MAE

---

## 🔮 Future Improvements

Potential enhancements include:

* Polynomial Regression
* Ridge Regression
* Lasso Regression
* Random Forest Regressor
* XGBoost Regressor
* Hyperparameter Tuning
* Cross Validation
* Feature Selection

These techniques may further improve prediction accuracy beyond the current **86% R² Score**.

---

## 👨‍💻 Author

**Shazzad**
Machine Learning Enthusiast | AI & Full-Stack Developer

> Built as a first end-to-end Machine Learning regression project to understand the complete ML pipeline from data exploration to model optimization through feature engineering. 🚀
