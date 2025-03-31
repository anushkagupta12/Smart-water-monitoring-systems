# Smart Water Monitoring System - Prediction Model

## 📌 Overview
This project predicts daily water consumption for individual households using machine learning techniques. The model is trained on historical usage patterns, household characteristics, weather conditions, and conservation behaviors.

---

## 📂 Dataset Description
### Dataset Files:
- **train.csv** - Training dataset (14000 x 12)
- **test.csv** - Test dataset (6000 x 11)
- **sample_submission.csv** - Sample submission format

### 🔹 Features Used
- **Timestamp** - Converted to time-based features (Hour, Day of Week, Month)
- **Residents** - Number of household members
- **Apartment_Type** - Encoded categorical feature
- **Temperature, Humidity** - Environmental factors
- **Water_Price** - Water pricing at the time
- **Period_Consumption_Index** - Relative water usage in an 8-hour period
- **Income_Level** - Household income level (encoded)
- **Guests** - Number of visitors
- **Amenities** - Encoded categorical feature
- **Appliance_Usage** - Whether water appliances are being used

---

## ⚙️ Model Training Process

### 1️⃣ Data Preprocessing
- Converted `Timestamp` to datetime and extracted `Hour`, `DayOfWeek`, and `Month`.
- Encoded categorical features (`Apartment_Type`, `Income_Level`, `Amenities`) using Label Encoding.
- Checked and handled missing values if necessary.

### 2️⃣ Model Selection & Training
- Used **XGBoost Regressor** for training due to its efficiency with tabular data.
- Performed train-validation split (80-20).
- Applied early stopping to prevent overfitting.

### 3️⃣ Prediction & Submission
- Predictions were generated on `test.csv`.
- Formatted output as `water_consumption_predictions.csv` with `Timestamp` as the index.

---

## 📦 Dependencies
To run the script, install the required Python libraries:
```bash
pip install pandas numpy scikit-learn xgboost
```

---

## 🚀 Running the Script
Ensure `train.csv` and `test.csv` are in the same directory as the script, then run:
```bash
python train_model.py
```
The generated predictions file (`water_consumption_predictions.csv`) will be ready for submission.

---


## 📑 Submission Format
The final CSV file must follow:
- **Columns**: `Timestamp`, `Water_Consumption`
- **Index**: `Timestamp`
- **Dimensions**: (6000 x 2)

---

## 📁 Files Included
- **train_model.py** - Machine Learning script
- **README.md** - This file - explaining the approach
- **water_consumption_predictions.csv** - Final output file

---

## 🔍 Notes
- **XGBoost** was chosen for its strong performance on structured data.
- Feature engineering focused on time-based and categorical encodings.
- Further improvements could include hyperparameter tuning and feature selection optimization.

---

🎯 **Happy Coding & Stay Hydrated!** 🚀💧

