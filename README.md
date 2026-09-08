# 🚗 Car Price Prediction using Multiple Linear Regression

## 📌 Project Overview

This project predicts the **price of a used car** using **Multiple Linear Regression**.

The model uses three important features:

* `year` — Manufacturing year of the car
* `km_driven` — Total kilometers driven
* `engine` — Engine capacity of the car

The project is implemented using **Python, Pandas, NumPy, Matplotlib, and Scikit-learn** in Jupyter Notebook.

---

## 🎯 Objective

The objective of this project is to build a machine learning model that predicts the price of a car based on its:

* Manufacturing year
* Kilometers driven
* Engine capacity

The project demonstrates the basic workflow of a **Multiple Linear Regression** problem.

---

## 🧠 Algorithm

### Multiple Linear Regression

Multiple Linear Regression is a supervised machine learning algorithm used to predict a continuous target variable using two or more independent variables.

The general equation is:

```text
Price = b₀ + b₁(Year) + b₂(Km_Driven) + b₃(Engine)
```

Where:

* `Price` = Predicted car price
* `b₀` = Intercept
* `b₁` = Coefficient of Year
* `b₂` = Coefficient of Km Driven
* `b₃` = Coefficient of Engine

---

## 📊 Features

| Feature     | Description                   | Type        |
| ----------- | ----------------------------- | ----------- |
| `year`      | Manufacturing year of the car | Independent |
| `km_driven` | Total kilometers driven       | Independent |
| `engine`    | Engine capacity               | Independent |
| `price`     | Selling price of the car      | Target      |

### Input Features

```text
X = [year, km_driven, engine]
```

### Target

```text
y = price
```

---

## 🔄 Machine Learning Workflow

```text
Dataset
   ↓
Load Dataset
   ↓
Data Exploration
   ↓
Data Cleaning
   ↓
Select Features
   ↓
Train-Test Split
   ↓
Multiple Linear Regression
   ↓
Model Training
   ↓
Prediction
   ↓
Model Evaluation
```

---

## 🛠️ Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Scikit-learn

---

## 📂 Project Structure

```text
Car-Price-Prediction/
│
├── Car_Price_Prediction.ipynb
├── car_data.csv
├── README.md
└── requirements.txt
```

---

## 🔍 Dataset

The dataset contains used-car information.

The important columns used for this project are:

```text
year
km_driven
engine
price
```

Other columns in the dataset may be ignored because this project focuses on demonstrating Multiple Linear Regression using these three features.

---

## 🧹 Data Preprocessing

Before training the model, the dataset is checked for:

* Missing values
* Incorrect data types
* Duplicate records
* Unnecessary columns

Example:

```python
df.info()
df.isnull().sum()
df.describe()
```

The required features are selected:

```python
X = df[['year', 'km_driven', 'engine']]
y = df['price']
```

---

## ✂️ Train-Test Split

The dataset is divided into training and testing data.

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Here:

* 80% of the data is used for training
* 20% of the data is used for testing

---

## 🤖 Model Training

A Multiple Linear Regression model is created using Scikit-learn.

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)
```

The model learns the relationship between:

```text
year
km_driven
engine
```

and:

```text
price
```

---

## 🔮 Prediction

After training, the model can predict prices for unseen data.

```python
y_pred = model.predict(X_test)
```

For example, the model can take:

```text
Year       = 2018
Km Driven  = 45000
Engine     = 1197
```

and produce an estimated car price.

---

## 📈 Model Coefficients

The trained model produces coefficients for each feature.

```python
print("Coefficients:", model.coef_)
print("Intercept:", model.intercept_)
```

The coefficients indicate how each feature contributes to the predicted price while keeping the other features constant.

The final regression equation can be represented as:

```text
Predicted Price =
Intercept
+ Coefficient₁ × Year
+ Coefficient₂ × Km Driven
+ Coefficient₃ × Engine
```

---

## 📊 Model Evaluation

The model can be evaluated using regression metrics such as:

### R² Score

Measures how well the model explains the variation in car prices.

```python
from sklearn.metrics import r2_score

r2 = r2_score(y_test, y_pred)

print("R² Score:", r2)
```

### Mean Absolute Error

```python
from sklearn.metrics import mean_absolute_error

mae = mean_absolute_error(y_test, y_pred)

print("MAE:", mae)
```

### Mean Squared Error

```python
from sklearn.metrics import mean_squared_error

mse = mean_squared_error(y_test, y_pred)

print("MSE:", mse)
```

### Root Mean Squared Error

```python
rmse = mse ** 0.5

print("RMSE:", rmse)
```

---

## 📌 Example Output

```text
Coefficients:
[... ...]

Intercept:
...

Actual Prices:
[...]

Predicted Prices:
[...]

R² Score:
...

MAE:
...

MSE:
...

RMSE:
...
```

The exact values depend on the dataset and train-test split.

---

## 💡 Key Learning Outcomes

Through this project, I learned:

* What Multiple Linear Regression is
* How multiple features are used for prediction
* How to select independent and dependent variables
* How to split data into training and testing sets
* How to train a regression model using Scikit-learn
* How to obtain coefficients and intercept
* How to make predictions
* How to evaluate a regression model
* How to interpret regression results

---

## 🚀 Future Improvements

This project can be improved by:

* Adding more relevant car features
* Handling categorical variables such as fuel type and transmission
* Performing feature scaling
* Removing outliers
* Using cross-validation
* Comparing Linear Regression with Ridge and Lasso Regression
* Trying Random Forest and other regression algorithms
* Deploying the model as a web application

---

## 👨‍💻 Author

**Ragul Balajee G K**

Computer Science & Engineering Student

---

## ⭐ Conclusion

This project demonstrates the use of **Multiple Linear Regression for used-car price prediction** using three features: `year`, `km_driven`, and `engine`.

It provides a practical introduction to the machine learning workflow, including **data preprocessing, feature selection, model training, prediction, and evaluation**.
