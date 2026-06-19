# Wall-Following Robot Navigation Classification

## Overview

This project was developed for the **Machine Learning 2** course. The objective is to predict the navigation action of a wall-following robot using sensor measurements collected while the robot moves around a room.

The project compares two machine learning algorithms:

* Support Vector Classifier (SVC)
* Random Forest Classifier

The models are evaluated before and after hyperparameter optimization using Grid Search.

---

## Dataset

The dataset contains sensor readings collected from a SCITOS G5 robot equipped with ultrasonic sensors.

### Features

The original sensor readings are simplified into four distance measurements:

* `SD_FRONT` – Distance measured in front of the robot
* `SD_LEFT` – Distance measured on the left side
* `SD_RIGHT` – Distance measured on the right side
* `SD_BACK` – Distance measured behind the robot

### Target Classes

The model predicts one of the following navigation actions:

* Move-Forward
* Slight-Right-Turn
* Sharp-Right-Turn
* Slight-Left-Turn

### Dataset Size

* 5,456 instances
* 4 input features
* 1 target label

---

## Project Workflow

### 1. Data Loading

The dataset is imported from a CSV file and loaded into a Pandas DataFrame.

### 2. Data Preprocessing

The dataset is divided into:

* 70% Training Set
* 15% Validation Set
* 15% Test Set

Feature scaling is performed using `StandardScaler`.

### 3. Model Training

Two machine learning models are trained:

#### Support Vector Classifier (SVC)

The SVC model is trained using:

* Default parameters
* Optimized parameters obtained through Grid Search

Hyperparameters tuned:

* `C`
* `gamma`

#### Random Forest Classifier

The Random Forest model is trained using:

* Default parameters
* Optimized parameters obtained through Grid Search

Hyperparameters tuned:

* `max_depth`
* `max_features`

### 4. Model Evaluation

The models are evaluated using:

* Accuracy Score
* Balanced Accuracy Score
* Confusion Matrix
* Successful Navigation Rate
* Collision Rate

---

## Results

### Support Vector Classifier (SVC)

| Configuration         | Accuracy |
| --------------------- | -------- |
| Default Parameters    | 94.01%   |
| Grid Search Optimized | 98.11%   |

### Random Forest

| Configuration         | Accuracy |
| --------------------- | -------- |
| Default Parameters    | 100.00%  |
| Grid Search Optimized | 100.00%  |

The Random Forest model achieved the best overall performance on the test dataset.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn
* Jupyter Notebook

---

## Repository Structure

```text
├── sensor_readings_4.csv
├── ML2_Mobina_Alinaghian.ipynb
├── Machine Learning 2.pdf
└── README.md
```

---

## How to Run

1. Clone the repository:

```bash
git clone <repository-url>
```

2. Install required packages:

```bash
pip install numpy pandas matplotlib scikit-learn
```

3. Open the Jupyter Notebook:

```bash
jupyter notebook
```

4. Run all notebook cells sequentially.

---

## Author

**Mobina Alinaghian**
