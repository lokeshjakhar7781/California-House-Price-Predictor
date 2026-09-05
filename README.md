# 🏠 California Housing Price Prediction

<p align="center">
  <b>Machine Learning Project for Predicting Median House Values</b>
</p>

---

## 📌 Overview

This project implements an end-to-end **Machine Learning pipeline for California housing price prediction**.

The model learns from housing-related features such as:

* 📍 Longitude
* 📍 Latitude
* 🏘️ Housing median age
* 🚪 Total rooms
* 🛏️ Total bedrooms
* 👨‍👩‍👧 Population
* 🏡 Households
* 💰 Median income
* 🌊 Ocean proximity

The objective is to predict the **median house value** for unseen housing records.

---

## ✨ Key Features

* 🔄 Automated data preprocessing
* 🧹 Missing-value handling
* 📊 Numerical feature standardization
* 🔤 Categorical feature encoding
* 🎯 Stratified train/test splitting
* 🌲 Random Forest regression
* 💾 Model persistence
* ⚡ Automatic training and inference
* 📁 CSV-based input/output workflow

---

## 🧠 Machine Learning Workflow

```text
                    ┌──────────────────┐
                    │   Housing Data   │
                    │   housing.csv    │
                    └────────┬─────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │ Feature Preparation │
                  └──────────┬──────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │ Stratified Data Split   │
                │     80% Train / 20%     │
                └────────────┬────────────┘
                             │
                             ▼
              ┌─────────────────────────────┐
              │      Preprocessing          │
              │                             │
              │ Numerical → Imputation      │
              │            → Scaling        │
              │                             │
              │ Categorical → Imputation    │
              │            → One-Hot Encode │
              └─────────────┬───────────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │ Random Forest     │
                  │    Regressor      │
                  └─────────┬─────────┘
                            │
                            ▼
                    ┌───────────────┐
                    │ Model +       │
                    │ Pipeline Saved│
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │  input.csv    │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │  Prediction   │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │  output.csv   │
                    └───────────────┘
```

---

## 🛠️ Technologies Used

| Technology       | Purpose                        |
| ---------------- | ------------------------------ |
| 💾 Joblib        | Model serialization            |
| 📄 CSV           | Dataset and prediction storage |
| 🌲 Random Forest | Regression model               |
| ⚙️ Pipeline      | Data preprocessing workflow    |

---

## 📂 Project Structure

```text
California-Housing-Price-Prediction/
│
├── 📄 main.py
├── 📊 housing.csv
├── 📥 input.csv
├── 📤 output.csv
├── 🤖 model.pkl
├── ⚙️ pipeline.pkl
└── 📖 README.md
```

### File Description

**`main.py`**
Contains the complete machine-learning workflow, including preprocessing, model training, model saving, and inference.

**`housing.csv`**
Main housing dataset containing **20,640 records and 10 columns**.

**`input.csv`**
Test/input dataset generated from the stratified split.

**`output.csv`**
Contains the predicted `median_house_value` for the input records.

**`model.pkl`**
Serialized trained Random Forest model.

**`pipeline.pkl`**
Serialized preprocessing pipeline.

---

## ⚙️ Preprocessing

The project automatically separates numerical and categorical attributes.

### Numerical Features

```text
Missing Values
      ↓
Median Imputation
      ↓
Standard Scaling
```

### Categorical Features

```text
Missing Values
      ↓
Most-Frequent Imputation
      ↓
One-Hot Encoding
```

Unknown categories are handled safely during prediction.

---

## 🌲 Machine Learning Model

The project uses a:

```text
Random Forest Regressor
```

The model is trained to predict:

```text
median_house_value
```

Random Forest is used to capture nonlinear relationships between housing characteristics and property values.

---

## 🔀 Data Splitting

The dataset is divided using a **stratified 80/20 split**.

The project creates an `income_cat` feature based on `median_income` and uses it during the split to maintain a similar income distribution between the training and test data.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/lokeshjakhar7781/California-House-Price-Predictor.git
cd California-House-Price-Predictor
```

### 2. Install Dependencies

```bash
pip install pandas numpy scikit-learn joblib
```

### 3. Run the Project

```bash
python main.py
```

---

## 🔄 How the Program Works

### First Run

If `model.pkl` does not exist, the program:

1. Loads `housing.csv`
2. Creates the income category
3. Performs a stratified split
4. Separates features and target
5. Builds the preprocessing pipeline
6. Transforms the training data
7. Trains the Random Forest model
8. Saves the trained model
9. Saves the preprocessing pipeline

### Subsequent Runs

If the trained model already exists, the program:

1. Loads the saved model
2. Loads the saved preprocessing pipeline
3. Reads `input.csv`
4. Applies the preprocessing pipeline
5. Generates predictions
6. Writes predictions to `output.csv`

---

## 📊 Prediction Output

The generated `output.csv` contains:

```text
median_house_value
```

The file contains predictions generated by the trained Random Forest model for the records provided in `input.csv`.

---

## 💡 Example

### Input

```text
longitude: -118.39
latitude: 34.12
housing_median_age: 29
total_rooms: 6447
total_bedrooms: 1012
population: 2184
households: 960
median_income: 8.2816
ocean_proximity: <1H OCEAN
```

### Predicted Output

```text
median_house_value: 483020.60
```

---

## 🎯 Project Goal

The goal of this project is to demonstrate a complete machine-learning workflow that transforms raw housing data into an automated prediction system.

```text
Raw Data
   ↓
Data Splitting
   ↓
Preprocessing
   ↓
Feature Transformation
   ↓
Random Forest
   ↓
House Price Prediction
```

---

<p align="center">
  <b>🏠 Turning Housing Data into Intelligent Predictions 🤖</b>
</p>
