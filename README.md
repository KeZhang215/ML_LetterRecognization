# Letter Recognition - Machine Learning Classification

## Overview
This repository contains the implementation for **Project #4** of **IEOR 242A: Machine Learning and Data Analytics (Fall 2024)**. The project focuses on building machine learning models for **optical character recognition** using a dataset of distorted images of the letters **A, B, P, and R**.

## Dataset
The dataset includes two CSV files:
- **`Letters_train_2024.csv`**: Contains 2181 observations for training.
- **`Letters_test_2024.csv`**: Contains 935 observations for testing.

Each observation represents a distorted image of one of the four letters and includes extracted numerical features derived from pixel distributions.

### Features:
The dataset consists of **various numerical attributes** describing the images, such as:
- **Bounding box properties** (`xbox`, `ybox`, `width`, `height`)
- **Pixel statistics** (`onpix`, `xbar`, `ybar`, `x2bar`, `y2bar`, `xybar`, etc.)
- **Edge properties** (`xedge`, `xedgeycor`, `yedge`, `yedgexcor`)
- **Target variable**: `letter` (A, B, P, or R)

## Tasks & Methodology

### 1. Binary Classification: Predicting Letter "B"
- Creating a binary variable `isB` (Yes = letter is B, No = otherwise).
- Implementing and comparing different models:
  - **Baseline Model**: Predicting the most frequent class.
  - **Logistic Regression**: Evaluating accuracy and AUC.
  - **CART (Decision Tree)**: Selecting `ccp_alpha` via cross-validation.
  - **Random Forest**: Evaluating performance with default parameters.

### 2. Multi-Class Classification: Predicting A, B, P, or R
- Implementing the following models:
  - **Baseline Model** (most frequent class)
  - **Linear Discriminant Analysis (LDA)**
  - **CART Decision Tree** (selecting `ccp_alpha` via cross-validation)
  - **Bagging (RandomForest with `max_features = total features`)**
  - **Random Forest** (optimizing `max_features` via cross-validation)
  - **Gradient Boosting** (fixed `n_estimators = 300`, `max_leaf_nodes = 15`)

## Reproducibility
- **Random state = 2024** is used for bagging and boosting models to ensure reproducibility.

