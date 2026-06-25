# Titanic Survival Prediction

## Overview

This project analyzes the Titanic dataset and builds multiple machine learning models to predict whether a passenger survived the disaster.

The project covers the complete machine learning workflow:

* Data Exploration
* Data Cleaning
* Feature Investigation
* Feature Engineering
* Data Encoding
* Model Training
* Model Evaluation
* Model Comparison

---

## Dataset

Dataset: Titanic Dataset

Target Variable:

* Survived

  * 0 = Did Not Survive
  * 1 = Survived

Original Features:

* PassengerId
* Survived
* Pclass
* Name
* Sex
* Age
* SibSp
* Parch
* Ticket
* Fare
* Cabin
* Embarked

Dataset Size:

* 891 Rows
* 12 Columns

---

## Data Exploration

Before building any model, the dataset was explored using:

* info()
* describe()
* Missing value analysis
* Distribution plots
* Correlation analysis

Missing values were found in:

| Column   | Missing Values |
| -------- | -------------- |
| Age      | 177            |
| Cabin    | 687            |
| Embarked | 2              |

---

## Data Cleaning

### Age

Missing Age values were filled using the median age.

Reason:

* Age contains outliers.
* Median is less affected by extreme values than mean.

### Embarked

Missing Embarked values were filled using the mode.

Reason:

* Embarked is a categorical feature.
* Mode represents the most frequent category.

### Cabin

The Cabin column was removed.

Reason:

* More than 75% of the values were missing.
* Insufficient data to make reliable imputations.

---

## Feature Investigation

Several features were analyzed against the target variable:

### Sex vs Survival

Female passengers had a significantly higher survival rate than male passengers.

### Passenger Class vs Survival

Passengers in higher classes had better survival chances.

### Age vs Survival

Age showed only a weak correlation with survival.

### Fare vs Survival

Passengers with higher fares generally had higher survival rates.

### Embarked vs Survival

Survival rates varied across embarkation locations.

### Family Features

The relationship between:

* SibSp
* Parch

and survival was analyzed.

A new feature called FamilySize was created.

---

## Feature Engineering

### FamilySize

Created using:

FamilySize = SibSp + Parch + 1

Purpose:

* Represents total family members traveling together.

---

### IsAlone

Created from FamilySize.

Values:

* Yes
* No

Purpose:

* Identifies passengers traveling alone.

---

### AgeGroup

Age was grouped into:

* Child
* Teen
* Adult
* Senior

Purpose:

* Easier interpretation of survival patterns by age category.

---

### FareGroup

Fare was grouped into:

* Low
* Medium
* High
* Very High

Purpose:

* Analyze survival rates across fare categories.

---

## Encoding

Machine learning models cannot directly process string values.

The following encodings were applied:

### Sex

* male → 1
* female → 0

### Embarked

* S → 1
* C → 2
* Q → 3

### IsAlone

* Yes → 1
* No → 0

---

## Machine Learning Models

The following features were used for training:

* Pclass
* sex_int
* Fare
* Embarked_int
* FamilySize
* IsAlone_int

Target:

* Survived

Dataset split:

* Training Data: 80%
* Testing Data: 20%

Random State:

* 42

Models trained:

### Logistic Regression

Used as a baseline classification model.

### Decision Tree

Used to learn decision rules from the data.

### Random Forest

Used to reduce overfitting by combining multiple decision trees.

### K-Nearest Neighbors (KNN)

Used as a distance-based classification model.

---

## Model Evaluation

Each model was evaluated using:

* Accuracy Score
* Classification Report
* Precision
* Recall
* F1 Score

The performance of all models was compared using a model comparison table.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn

---

## What I Learned

Through this project I learned:

* Data Cleaning
* Handling Missing Values
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Correlation Analysis
* Data Encoding
* Logistic Regression
* Decision Trees
* Random Forests
* K-Nearest Neighbors
* Model Evaluation
* Machine Learning Workflow

---

## Future Improvements

Possible improvements include:

* Hyperparameter Tuning
* Cross Validation
* Additional Feature Engineering
* Advanced Classification Models
* Feature Selection Techniques
