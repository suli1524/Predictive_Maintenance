# Predictive Maintenance with Milling Machine Dataset

## Overview
In many industrial settings, the reliability and optimal performance of machines are critical to maintaining smooth operation. The challenge lies in addressing unexpected machine failures and unplanned downtime, which leads to financial losses and operation disruption.tThe objective is to develop a predictive maintenance model to anticipate and address potential machine failures before they occur.  Creating a model which aims to leverage historical data to create a maintenance schedule to improve operation efficiency.
This repository contains a synthetic dataset modeling a milling machine's operation, designed for predictive maintenance applications. The dataset comprises 10,000 data points, each represented by 14 features. These features include information about product quality, temperature, rotational speed, torque, tool wear, and machine failures.

## Dataset Description

### Features

1. **UID**: Unique identifier ranging from 1 to 10,000.
2. **Product ID**: Product quality variant (L, M, or H) with a variant-specific serial number.
3. **Type**: Product type (L, M, or H).
4. **Air Temperature [K]**: Generated using a random walk process, later normalized to a standard deviation of 2 K around 300 K.
5. **Process Temperature [K]**: Generated using a random walk process, normalized to a standard deviation of 1 K, added to the air temperature plus 10 K.
6. **Rotational Speed [rpm]**: Calculated from a power of 2860 W, overlaid with normally distributed noise.
7. **Torque [Nm]**: Normally distributed torque values around 40 Nm with a standard deviation of 10 Nm and no negative values.
8. **Tool Wear [min]**: Tool wear time influenced by product quality variants (H/M/L), adding 5/3/2 minutes, respectively.
9. **Machine Failure**: A binary label indicating whether the machine has failed (1) or not (0).

### Failure Modes

- **Tool Wear Failure (TWF)**: Randomly selected tool wear time between 200 - 240 mins, leading to tool replacement or failure.
- **Heat Dissipation Failure (HDF)**: Process failure if the difference between air- and process temperature is below 8.6 K, and rotational speed is below 1380 rpm.
- **Power Failure (PWF)**: Process failure if power is below 3500 W or above 9000 W, calculated from torque and rotational speed.
- **Overstrain Failure (OSF)**: Process failure if the product of tool wear and torque exceeds certain thresholds based on product variants.
- **Random Failures (RNF)**: 0.1% chance of process failure regardless of process parameters.

## Usage

1. **Data Exploration**: Explore the dataset to understand its structure and relationships between features.
2. **Data Preprocessing**: Handle missing values, normalize features, and encode categorical variables if necessary.
3. **Feature Engineering**: Create new features or transformations to enhance model performance.
4. **Model Training**: Use machine learning algorithms to train a predictive maintenance model.
5. **Evaluation**: Assess the model's performance using appropriate metrics.
6. **Machine Learning Models and Results**:
   - Model 1: [Random Forest model ]
     - Accuracy: [97.77]
   - Model 2: [Randon Forest model w/ XGBoost]
     - Accuracy: [94.72]

7. **Citation**: original publication: S. Matzka, "Explainable Artificial Intelligence for Predictive Maintenance Applications," 2020 Third International Conference on Artificial Intelligence for Industries (AI4I), doi: 10.1109/AI4I49448.2020.00023.

## Conclusion

Using the Random Forest model, we are able to create a predictive maintenance model which correctly identify a machine failure with a 97.77% accuracy.The recommendations to better improve the accuracy, is to get more data since were limit to a synthetic dataset, add more features such as inspection/ maintenance schedule, runtime data, lifetime of machine counterparts.Following  those recommendations we would be able to automate the data, allowing us to create a app that would give out alerts for when preventative maintenance should be done.

  

