# Credit Card Score Prediction using Machine Learning

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Approach](#approach)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [EDA and Feature Engineering](#eda-and-feature-engineering)
- [Modeling](#modeling)
- [Challenges and Improvements](#challenges-and-improvements)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
The purpose of this project is to predict the **credit card score** of customers (whether "good" or "bad") using **classification models** based on various features. The prediction helps financial institutions assess creditworthiness and make better lending decisions.

### Key Features:
- **Classification problem** predicting whether a customer has a "Good" or "Bad" credit score.
- Models used: **K-Nearest Neighbors (KNN)**, **Random Forest**, and **Logistic Regression**.
- Extensive **Exploratory Data Analysis (EDA)** to clean and preprocess the data, including outlier detection and removal of irrelevant columns.

## Dataset
The dataset includes various customer features that may influence their credit card score, such as:
- Age
- Annual Income
- Credit History (length, defaults)
- Spending Patterns
- Payment Behavior

### Example Dataset Format:
| Age | Income | Credit History | Spending | Defaults | Score (Label) |
|-----|--------|----------------|----------|----------|---------------|
| 32  | 50000  | 7 years        | Medium   | 0        | Good          |
| 45  | 120000 | 10 years       | High     | 1        | Bad           |

The target variable is **binary**, representing the customer's credit score as either **Good** or **Bad**.

## Approach
### 1. **Exploratory Data Analysis (EDA)**:
   - Conducted EDA to explore the data, understand feature distributions, and identify trends.
   - Removed columns that were irrelevant or did not add value to the model (e.g., customer IDs).
   - Handled missing values and detected outliers, which were either removed or transformed.

### 2. **Feature Engineering**:
   - Encoded categorical variables (e.g., spending patterns) into numerical values.
   - Scaled features such as **income** and **credit history** to ensure consistency.

### 3. **Model Building**:
   - Implemented three classification algorithms:
     - **K-Nearest Neighbors (KNN)**: A simple, distance-based model.
     - **Random Forest**: An ensemble learning method combining multiple decision trees.
     - **Logistic Regression**: A baseline linear classifier for binary classification.

## Project Structure
```
Credit-Card-Score-Prediction/
│
├── data/
│   ├── credit_card_data.csv             # Dataset used for the project
│
├── notebooks/
│   ├── data_preprocessing.ipynb         # Data preprocessing and cleaning
│   ├── model_building.ipynb             # Model building and evaluation
│
├── src/
│   ├── data_processing.py               # Data processing functions
│   ├── model_knn.py                     # K-Nearest Neighbors model
│   ├── model_logistic_regression.py     # Logistic Regression model
│   ├── model_random_forest.py           # Random Forest model
│
├── README.md                            # Project documentation
└── requirements.txt                     # Python package requirements
```

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/username/Credit-Card-Score-Prediction.git
   cd Credit-Card-Score-Prediction
   ```

2. **Install Required Packages**:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. **Prepare the Dataset**:
   Ensure the `credit_card_data.csv` file is placed in the `data/` directory.

2. **Run Data Processing**:
   Preprocess the dataset by executing:
   ```bash
   python src/data_processing.py
   ```

3. **Train Models**:
   - K-Nearest Neighbors:
     ```bash
     python src/model_knn.py
     ```
   - Logistic Regression:
     ```bash
     python src/model_logistic_regression.py
     ```
   - Random Forest:
     ```bash
     python src/model_random_forest.py
     ```

4. **Evaluate Models**:
   Compare model performance using accuracy and other evaluation metrics.

## EDA and Feature Engineering
1. **Outlier Removal**:
   - Identified and removed outliers that could negatively impact the model's performance, particularly in features like income and credit history.

2. **Dropped Unnecessary Columns**:
   - Columns that did not contribute to the prediction (e.g., IDs or unrelated personal data) were removed during the preprocessing phase.

3. **Categorical Encoding**:
   - Categorical features, such as spending patterns and default status, were encoded into numerical representations.

4. **Scaling**:
   - Features were scaled for consistent ranges to improve the performance of distance-based models like KNN.

## Modeling
Three models were implemented and trained:

- **K-Nearest Neighbors (KNN)**:
  - A simple algorithm that predicts the class of a sample based on the majority class of its nearest neighbors.

- **Logistic Regression**:
  - A linear model that estimates the probability of a binary outcome based on a linear combination of input features.

- **Random Forest**:
  - An ensemble method that creates a multitude of decision trees during training and outputs the mode of the classes for classification tasks.

## Challenges and Improvements
### Challenges:
- **Data Imbalance**: The dataset may have an unequal number of "Good" and "Bad" credit score labels, which could affect model performance.
- **Outliers**: Managing outliers was crucial to prevent them from skewing the results of models like KNN.

### Improvements:
- Consider **balancing techniques** like **SMOTE** or **undersampling** to address class imbalance.
- Further tuning the hyperparameters for **Random Forest** to boost accuracy and avoid overfitting.

## Contributing
Contributions are welcome! Feel free to fork the repository, create a new branch, and submit a pull request.

## License
This project is licensed under the **MIT License**.

---

This README file covers the main aspects of your project, including data preprocessing (EDA), model building, and usage instructions. You can modify the details to fit your exact implementation.
