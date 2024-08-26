# Common Variable Names in Machine Learning

This document outlines the common variable names and conventions used in machine learning projects, providing a quick reference for naming standards.

## Overview

| Variable Name       | Description                                                                                     |
| ------------------- | ----------------------------------------------------------------------------------------------- |
| `X`                 | Represents input features (independent variables) in a dataset. Typically a matrix or 2D array. |
| `y`                 | Represents the target variable (dependent variable). Typically a 1D array or vector.            |
| `X_train`, `X_test` | Subsets of `X` used for training and testing the model, respectively.                           |
| `y_train`, `y_test` | Subsets of `y` used for training and testing the model, respectively.                           |
| `X_val`, `y_val`    | Subsets used for validation during model training, often in cross-validation.                   |
| `y_pred`            | The predicted target values output by the model.                                                |
| `model`             | The machine learning model instance, e.g., `LinearRegression()` or `DecisionTreeClassifier()`.  |
| `n_samples`         | The number of samples (rows) in the dataset.                                                    |
| `n_features`        | The number of features (columns) in the dataset.                                                |
| `df`                | A DataFrame in pandas holding the tabular data.                                                 |
| `mean`, `std`       | Simple statistics representing the mean and standard deviation of a dataset, respectively.      |

## Capitalization Conventions

| Convention            | Explanation                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------- |
| **Capitalized Names** | Used for matrices, 2D arrays, or DataFrames. Examples: `X`, `X_train`, `X_test`.               |
| **Lowercase Names**   | Used for single-dimensional arrays (vectors) or scalar values. Examples: `y`, `model`, `mean`. |

## Examples in Context

```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score
import pandas as pd

# Example DataFrame
df = pd.DataFrame({
    'feature1': [1, 2, 3, 4, 5],
    'feature2': [10, 20, 30, 40, 50],
    'target': [0, 0, 1, 1, 1]
})

# Splitting data into features and target
X = df[['feature1', 'feature2']]
y = df['target']

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Model initialization
model = LogisticRegression()

# Model training
model.fit(X_train, y_train)

# Making predictions
y_pred = model.predict(X_test)

# Evaluating model
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy}")
```

## Summary Cheat Sheet

| Variable Name             | Description                                         |
| ------------------------- | --------------------------------------------------- |
| `X`                       | Input features (capitalized because it’s a matrix). |
| `y`                       | Target variable (lowercase because it’s a vector).  |
| `X_train`, `X_test`       | Training and testing data for input features.       |
| `y_train`, `y_test`       | Training and testing data for the target variable.  |
| `y_pred`                  | Predicted values from the model.                    |
| `model`                   | The machine learning model instance.                |
| `n_samples`, `n_features` | Number of samples and features in the dataset.      |
| `df`                      | A DataFrame (pandas) holding the data.              |

This naming convention helps make your code readable and understandable to anyone familiar with machine learning, ensuring consistency across projects and teams.
