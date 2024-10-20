

# Credit Card Fraud Detection

This repository contains a machine learning project aimed at detecting fraudulent credit card transactions using various classification algorithms. The dataset used is highly imbalanced, with fraudulent transactions making up only a small fraction of the total. This project demonstrates how to handle such imbalanced datasets using resampling techniques and model evaluation metrics beyond simple accuracy.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Model Evaluation](#model-evaluation)
- [Results](#results)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

## Overview

The objective of this project is to create a machine learning pipeline capable of detecting credit card fraud based on transactional data. Given the highly imbalanced nature of the dataset, traditional models tend to be biased towards the majority class. To address this, resampling techniques like SMOTETomek are used, and model evaluation is done with precision, recall, and F1-score, focusing specifically on the minority class (fraudulent transactions).

**Techniques used:**
- Data preprocessing and exploration
- Handling missing values and duplicates
- Class balancing with SMOTETomek
- Model training with Stratified K-Fold cross-validation
- Hyperparameter tuning for XGBoost, Decision Tree, and Random Forest
- Feature importance analysis for model interpretability

## Dataset

The dataset used for this project contains credit card transactions made by European cardholders in September 2013. The dataset consists of 284,807 transactions, where only 492 (0.172%) are fraudulent.

- **Time:** The number of seconds elapsed between this transaction and the first transaction in the dataset.
- **V1-V28:** Features resulting from Principal Component Analysis (PCA) transformation.
- **Amount:** The transaction amount, which can be used for cost-sensitive learning.
- **Class:** The target variable, where 0 represents legitimate transactions and 1 represents fraud.

The dataset is publicly available on Kaggle: [Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud).

## Project Structure

```
Credit Card Fraud Detection/
│
├── data/                         # Contains the dataset (not included in the repo, download from Kaggle)
│   └── creditcard.csv
├── notebooks/
│   └── fraud_detection.ipynb      # Jupyter notebook with full analysis and code
├── images/                        # Contains generated plots and figures for README (optional)
├── README.md                      # Project documentation
└── requirements.txt               # Python dependencies for the project
```

## Installation

To run this project, follow the steps below:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/shubh3781/-Brainwave_Matrix_Intern_Credit-Card-Frauds-Detection
   cd Credit-Card-Fraud-Detection
   ```

2. **Install the required dependencies:**

   It is recommended to use a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate    # On Windows use: venv\Scripts\activate
   ```

   Install dependencies from `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

3. **Download the dataset:**

   Download the dataset from Kaggle and place it in the `data/` directory.

   Kaggle link: [Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud)

## Usage

Once the environment is set up, you can run the Jupyter notebook to execute the entire analysis, or specific sections of the project:

```bash
jupyter notebook notebooks/fraud_detection.ipynb
```

The notebook covers:
- Data exploration and preprocessing
- Resampling with SMOTETomek
- Model training and evaluation with hyperparameter tuning
- Feature importance analysis

## Model Evaluation

This project evaluates three machine learning models:
- **XGBoost Classifier**
- **Decision Tree Classifier**
- **Random Forest Classifier**

Evaluation metrics used:
- **Precision, Recall, and F1-Score:** These metrics provide a more complete understanding of model performance, especially in the context of highly imbalanced data.
- **Confusion Matrix:** Gives insights into false positives and false negatives.
- **Feature Importance:** Helps understand which features contribute most to predicting fraudulent transactions.

## Results

The Random Forest classifier showed the best performance in detecting fraudulent transactions with the following metrics:
- **Precision for Class 1 (Fraud):** 0.86
- **Recall for Class 1 (Fraud):** 0.76
- **F1-Score for Class 1 (Fraud):** 0.80

These results indicate a good balance between precision and recall, minimizing false positives while still identifying a significant number of fraud cases.

## Future Work

- **Threshold Tuning:** Adjusting classification thresholds to better balance precision and recall.
- **Cost-Sensitive Learning:** Incorporating cost-sensitive methods to account for the unequal costs of false positives and false negatives.
- **Real-Time Detection:** Exploring the deployment of the model in a real-time system to flag fraudulent transactions instantly.

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request. For major changes, please open an issue to discuss the changes first.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

