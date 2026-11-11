
# Used Car Price Prediction

[فارسی](README.fa.md) | **English**

A machine learning project that explores used-car listings and develops models to estimate vehicle prices from features such as brand, model year, mileage, engine specifications, fuel type, and transmission.

The project is organized into five stages: exploratory data analysis, data cleaning, feature engineering, baseline model training, and model comparison.

## 📌 Project Highlights

- Started with **4,023 listings** and 12 columns.
- Retained **3,981 rows** after data cleaning and feature preparation.
- Extracted horsepower, engine size, and engine type from the raw `engine` column.
- Standardized transmission values into five groups: Automatic, Manual, CVT, Dual Shift, and Other.
- Compared three machine learning models: Linear Regression, Decision Tree, and Random Forest.
- Random Forest achieved the strongest reported performance:
  - **R²:** 0.747
  - **MAE:** approximately $9,489
  - **RMSE:** approximately $19,580

## 📂 Repository Structure

```text
.
├── data/
│   └── README.md
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_model_training.ipynb
│   └── 05_model_comparison.ipynb
├── models/
│   ├── model.pkl
│   └── best_model.pkl
├── reports/
│   ├── phase1_report.pdf
│   ├── phase2_report.pdf
│   ├── phase3_report.pdf
│   ├── phase4_report.pdf
│   └── phase5_report.pdf
├── README.md
└── README.fa.md
```

## 📊 Dataset

The dataset was provided by an educational institute.

The original dataset and processed CSV files are not included in this repository because permission for public redistribution has not been confirmed.

The notebooks and reports document the analysis and modeling workflow. Reproducing the complete workflow requires access to an authorized copy of the dataset.

## 🔬 Project Workflow

### Phase 1: Exploratory Data Analysis (EDA)

- Explored 4,023 rows and 12 columns.
- Examined numerical and categorical features.
- Studied price and mileage distributions and relationships between vehicle characteristics and price.
- Identified missing values in `clean_title` (598), `fuel_type` (170), `accident` (114), and `price` (28).

### Phase 2: Data Cleaning

- Removed 14 fully duplicated rows.
- Dropped rows with missing target values (`price`).
- Filled missing values in selected categorical columns using appropriate strategies.
- Reviewed outliers in price and mileage and retained plausible values.
- Checked for negative values and implausible model years.

### Phase 3: Feature Engineering

- Extracted **horsepower**, **engine size**, and **engine type** from the `engine` text column.
- Standardized more than 60 raw transmission labels into five groups: Automatic, Manual, CVT, Dual Shift, and Other.
- Applied encoding to categorical variables:
  - Label Encoding for selected categorical features.
  - One-Hot Encoding for fuel type and standardized transmission groups.
- Removed selected redundant or unused columns.
- Produced a feature-engineered dataset with **3,981 rows and 21 columns**.

### Phase 4: Model Training (Baseline)

- Trained **Linear Regression** as the baseline model.
- Used an 80/20 train/test split.
- Evaluated performance using MAE, MSE, RMSE, and R².
- Reviewed actual-versus-predicted results.

### Phase 5: Model Comparison

Three models were evaluated on the same test split:

| Model             | R² Score  | RMSE       | MAE       |
| ----------------- | --------- | ---------- | --------- |
| Linear Regression | 0.444     | 29,025     | 16,551    |
| Decision Tree     | 0.478     | 28,116     | 12,724    |
| **Random Forest** | **0.747** | **19,580** | **9,489** |

Random Forest achieved the best reported results among the three models. Its ability to capture non-linear relationships may help explain its stronger performance on this dataset.

**Most important features (Random Forest):** mileage, engine size, and horsepower.

## 📑 Reports

The `reports/` directory contains five PDF reports documenting each stage of the project, from exploratory analysis to final model comparison.

## 🤖 Saved Models

The `models/` directory contains two serialized model files:

- `model.pkl`: Baseline model.
- `best_model.pkl`: Best-performing Random Forest model.

**Important:** Only load Pickle files from trusted sources. Loading an untrusted `.pkl` file can execute arbitrary code. The saved models may also depend on the exact feature columns, preprocessing steps, and library versions used during training.

The dataset is not included, so these model files are provided as project artifacts rather than as a guarantee that the complete workflow can be reproduced from this repository alone.

## ⚠️ Limitations and Future Work

- The best model's MAE is approximately $9.5k, so predictions may not be accurate enough for real-world pricing decisions.
- The `model` feature was dropped; extracting useful information from model names may improve performance.
- Missing horsepower and engine-size values were filled using a simple statistical approach; more advanced imputation may improve results.
- Potential future improvements:
  - Apply a log transformation to the target variable (`price`).
  - Evaluate Gradient Boosting, XGBoost, or LightGBM.
  - Tune hyperparameters using cross-validation.
  - Compare preprocessing pipelines and feature-scaling strategies.
  - Build an interactive application using Streamlit or Flask.

## 🛠️ Tech Stack

Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn · Jupyter Notebook

## 📄 License

No license has been specified yet. All rights reserved unless permission is granted by the author.

## 👤 Author

**Rose Mirboloki**

[GitHub Profile](https://github.com/rosimirbolok-sudo)

