
# Random Forest Classifier - German Credit Dataset

A machine learning project that implements a Random Forest classifier to predict credit risk classification on the German Credit dataset. This project demonstrates feature engineering, data preprocessing, and model evaluation techniques.

## Overview

This repository contains a Jupyter Notebook that builds a predictive model to classify credit risk as "good" or "bad" using the German Credit dataset. The project showcases:

- Data loading and exploratory analysis
- Handling missing values
- Feature encoding (nominal and ordinal features)
- Train-test split with stratification
- Random Forest model training and evaluation
- Feature importance analysis via dimensionality reduction
- Model performance metrics and visualization

## Dataset

**German Credit Dataset** - A classic credit classification dataset containing:

- **1,000 credit records** from a German bank
- **10 input features** describing applicant demographics and credit characteristics
- **Target variable**: Credit Risk (Good/Bad)

### Features

| Feature | Type | Description |
|---------|------|-------------|
| Age | Numeric | Age of the credit applicant |
| Sex | Nominal | Gender (male/female) |
| Job | Ordinal | Employment level (0-3) |
| Housing | Nominal | Housing situation (own/rent/free) |
| Saving accounts | Ordinal | Savings level (none/little/moderate/quite rich/rich) |
| Checking account | Ordinal | Checking account balance (none/little/moderate/rich) |
| Credit amount | Numeric | Credit amount requested |
| Duration | Numeric | Credit duration in months |
| Purpose | Nominal | Purpose of credit (car, business, education, etc.) |
| Risk | Target | Credit classification (good/bad) |

## Project Structure

```
├── README.md                                    # This file
├── dim_reduction_german_credit_data.ipynb      # Main Jupyter Notebook
├── german_credit_data.csv                      # Dataset
└── .gitignore                                   # Git ignore file
```

## Requirements

```
pandas
scikit-learn
matplotlib
numpy
jupyter
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/arnabmitra471/random-forest-classifier-german_credit_dataset.git
cd random-forest-classifier-german_credit_dataset
```

2. Install required packages:
```bash
pip install pandas scikit-learn matplotlib numpy jupyter
```

## Usage

1. Launch Jupyter Notebook:
```bash
jupyter notebook
```

2. Open `dim_reduction_german_credit_data.ipynb`

3. Run all cells to:
   - Load and explore the German Credit dataset
   - Handle missing values
   - Encode categorical and numerical features
   - Train the Random Forest classifier
   - Evaluate model performance
   - Analyze feature importance

## Methodology

### 1. Data Loading & Exploration
- Load the German Credit dataset from CSV
- Examine data structure and distributions
- Identify missing values

### 2. Data Preprocessing
- **Missing Value Handling**: Fill missing values with "none" for categorical features
- **Target Variable Encoding**: Encode credit risk using LabelEncoder (good=0, bad=1)

### 3. Feature Engineering
- **Numeric Features**: Age, Credit amount, Duration
- **Ordinal Features**: Saving accounts, Checking account, Job (with explicit ordering)
- **Nominal Features**: Sex, Housing, Purpose (with one-hot encoding)

### 4. Feature Encoding Strategy
- **ColumnTransformer** pipeline for preprocessing:
  - Numeric features: Pass-through
  - Ordinal features: OrdinalEncoder with explicit category ordering
  - Nominal features: OneHotEncoder

### 5. Model Training
- **Train-Test Split**: 80-20 split with stratification
- **Algorithm**: Random Forest Classifier
- **Model Evaluation**: Accuracy, Confusion Matrix, Classification Report, ROC-AUC score

### 6. Model Analysis
- **Feature Importance**: Extract important features using SelectFromModel
- **Performance Metrics**: Confusion matrix and ROC curve visualization

## Key Results

The notebook generates:
- **Accuracy scores** on both training and testing sets
- **Confusion matrix** visualization
- **Classification report** with precision, recall, and F1-scores
- **ROC-AUC curve** for binary classification performance
- **Feature importance rankings**

## Notebook Contents

The Jupyter Notebook is organized into the following sections:

1. **Imports** - Load necessary libraries
2. **Loading the dataset** - Read German Credit CSV
3. **Handling missing values** - Fill NaN values
4. **Encoding target variable** - Convert risk to numerical labels
5. **Encoding input features** - Separate and encode features
6. **Dividing categorical features** - Identify ordinal vs. nominal features
7. **Defining category orders** - Set explicit orderings for ordinal features
8. **Splitting dataset** - Create train-test sets
9. **Model training** - Fit Random Forest classifier
10. **Model evaluation** - Calculate metrics and visualizations
11. **Feature importance** - Analyze feature contributions

## Model Performance

The Random Forest classifier provides:
- High accuracy in predicting credit risk
- Feature importance rankings for interpretability
- Robust handling of mixed data types
- Good generalization via ensemble methods

## Technologies Used

- **Python 3.x**
- **Jupyter Notebook** - Interactive development
- **Pandas** - Data manipulation
- **Scikit-learn** - Machine learning
- **Matplotlib** - Data visualization

## Future Improvements

- Add cross-validation for more robust evaluation
- Hyperparameter tuning (n_estimators, max_depth, etc.)
- Compare with other algorithms (Gradient Boosting, SVM, etc.)
- Feature scaling and normalization experiments
- Class imbalance handling techniques (SMOTE, class weights)
- Model interpretability with SHAP values

## License

This project is open source and available under the MIT License.

## Author

Arnab Mitra

## References

- German Credit Dataset: [Kaggle Hub]([https://archive.ics.uci.edu/ml/datasets/german+credit+data](https://www.kaggle.com/datasets/kabure/german-credit-data-with-risk))
- Scikit-learn Documentation: [RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)

## Contributing

Contributions are welcome! Feel free to:
- Report issues
- Suggest improvements
- Submit pull requests

## Questions?

For questions or feedback, please open an issue in the repository.
