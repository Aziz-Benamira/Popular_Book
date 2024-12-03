# Predicting Book Popularity for E-Commerce Optimization

## Overview

This project focuses on predicting the popularity of books sold in an online bookstore using machine learning. Identifying popular products is crucial for e-commerce businesses to maximize revenue and manage inventory efficiently. 

## Dataset

The dataset includes the following features for each book:

- **price**: Book price in USD.
- **review/helpfulness**: A ratio indicating helpfulness votes for reviews.
- **review/summary**: Short summaries of reviews.
- **review/text**: Full text of reviews.
- **authors**: Book authors.
- **categories**: Genres/categories of the book.
- **popularity**: Target variable (Popular/Unpopular).

---

## Features Used in the Model

The project utilizes a combination of numerical, categorical, and text-based features. Below is a summary of how these features are processed:

1. **Numerical Features**:
   - **Price**: Scaled using `StandardScaler` for normalization.
   - **Helpfulness Ratio**: Calculated as `helpful_votes / total_votes`.

2. **Text Features**:
   - **Review Summary** and **Review Text**: Processed with `TfidfVectorizer` to create sparse matrices representing key terms.

3. **Categorical Features**:
   - **Authors**: Encoded using `LabelEncoder`.
   - **Categories**: One-hot encoded to create dummy variables.

4. **Target Variable**:
   - Mapped to binary labels: `1` for **Popular** and `0` for **Unpopular**.

---

## Model and Training

- **Model Used**: Random Forest Classifier
- **Hyperparameters**:
  - Number of estimators: 100
  - Splitting criterion: Gini impurity
  - Minimum samples per split: 2
  - Random state: 42 (for reproducibility)

### Training Process
1. Combined all features (numerical, text, and categorical) into a sparse matrix using `scipy.sparse.hstack`.
2. Split the dataset into training (80%) and testing (20%) sets.
3. Trained the Random Forest model on the training set.
4. Evaluated the model on the test set.

---

## Results

The model achieved an accuracy of **76%** on the test set, meeting the project's target. Further tuning and feature engineering could improve this performance.

---

## Contributing

Feel free to fork this repository and submit pull requests for improvements or new features.

---

