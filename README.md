# 🏎️ Formula 1 - Race Outcome Prediction

This repository explores predictive modeling of Formula One race outcomes using structured race data from Kaggle, using regression and classification techniques to analyze the relationship between conditions and race performance:
https://www.kaggle.com/datasets/vshreekamalesh/comprehensive-formula-1-dataset-2020-2025 

## Overview

  * **Challenge:**  The objective is to model and predict Formula One race outcomes using tabular race data. Specifically, the task is to determine how pre-race and in-race variables (such as grid position, constructor, and performance metrics) influence a driver’s finishing position.
  * **Approach:** This project formulates the problem as both a regression task (predict exact finishing position) and a classification task (predict whether a driver finishes in the top 10).
   ML models implemented: Linear Regression and Decision Tree Classifier.
  * **Performance Summary:** The classification model achieved solid accuracy in predicting top 10 finishes, showing that starting grid position and team performance are strong predictors. The regression model showed moderate error, indicating the complexity of race outcomes.

## Summary of Workdone

### Data

* Dataset:
  * Type:
    * Input: CSV file containing race data (drivers, grid position, constructors, lap times, etc.)
    * Output: Regression: finishing position, Classification: top 10 finish (binary)
  * Size: Dataset includes multiple seasons (2020–2025). Thousands of race entries

* Preprocessing / Cleaning: 
  * Removed or handled missing values using forward fill and drop methods
  * Converted categorical variables (constructor, driver) using one-hot encoding
  * Created new feature: top10 (1 if position ≤ 10, else 0)

* Data Visualization: 
  * Scatter plot of grid position vs finishing position showed strong correlation
  * Observed that drivers starting near the front tend to finish higher
  * Some variability exists due to race conditions and performance

### Problem Formulation

* Define:
  * Input:
    * Grid position
    * Constructor (encoded)
    * Driver (encoded)
    * Performance metrics
  * Output:
    * Regression: finishing position
    * Classification: top 10 (binary)
  * Models: 
    * Linear Regression → baseline for regression
    * Decision Tree Classifier → interpretable classification model
  * Hyperparameters:
    * Default sklearn parameters used for simplicity
    * Train/test split: 80/20

### Training

* Method: 
  * Implemented using Python and scikit-learn
  * Trained on local machine (Jupyter Notebook)
* Training Time: 
  * Very fast (few seconds due to small dataset size)
* Training Process: 
  * Fit model on training data
  * Evaluated on test data
* Stopping Criteria: 
  * Single-pass training (no iterative epochs required)
* Challenges: 
  * Handling categorical variables
  * Managing missing values

### Performance Comparison

* Metrics: 
  * Regression: Mean Squared Error (MSE)
  * Classification: Accuracy
* Results:
  
| Model | Task | Performance |
| :--- | :---: | ---: |
| Linear Regression | Regression | Moderate MSE |
| Decision Tree | Classification | Good Accuracy |

### Conclusions

* Grid position is a strong predictor of race outcome
* Team (constructor) also significantly impacts performance
* Race outcomes are not perfectly predictable due to randomness (pit stops, weather, crashes)

### Future Work

* Implement a Random Forest ML model
* Include additional features such as weather conditions and pit stop strategies
* Use time-series modeling for race progression
* Perform hyperparameter tuning

## Visualizations

*
<img width="759" height="590" alt="image" src="https://github.com/user-attachments/assets/bee218c7-c6af-4205-9cf8-e16807ff5866" />
*
<img width="1089" height="490" alt="image" src="https://github.com/user-attachments/assets/e2a8f6f2-6d78-49b5-bd8f-5f589e9c48a3" />
*
<img width="689" height="489" alt="image" src="https://github.com/user-attachments/assets/4ec78bec-d5e5-4c3d-87e7-6093df35d0ec" />
*
<img width="557" height="489" alt="image" src="https://github.com/user-attachments/assets/869cd897-60be-4e93-b8dd-0a6ff54ae190" />
*
<img width="1589" height="590" alt="image" src="https://github.com/user-attachments/assets/b89ca918-9889-4c28-87ad-baa34ba0d065" />

## Results Reproduction

1. Download Dataset: 
https://www.kaggle.com/datasets/vshreekamalesh/comprehensive-formula-1-dataset-2020-2025

2. Run Notebook
Open the notebook (F1.ipynb)
Run all cells step-by-step

3. Modify
You can change the target variable or model to experiment further

### Overview of files in repository

  * Kaggle Tabular Data.ipynb - Project Instruction file
  * F1.ipynb - Code file
  * dataset-metadata.json - json file
  * f1_2024_constructor_standings.csv - Constructor/Team data
  * f1_2024_driver_standings.csv - Driver Standings data
  * f1_2024_race_results.csv - Race Results data
  * f1_circuits_metadata.csv - Circuit/Track data
  * f1_historical_drivers.csv - Historical Drivers data
  * f1_qualifying_results_2024.csv - Qualifying Results data

### Software Setup
* Necessary Packages:
  * Numpy
  * Pandas
  * Seaborn
  * Matplotlib
  * Scikit-learn
* Installation Code: pip install pandas numpy matplotlib scikit-learn
* Environment: Python (Jupyter Notebook)

### Data

* Download from Kaggle (link above)
* Place CSV file in same directory as notebook
* No heavy preprocessing required beyond notebook steps

### Training

* Run all cells in the notebook
* Model will train automatically

#### Performance Evaluation

* Regression:
  * Mean Squared Error (MSE) printed in output
* Classification:
  * Accuracy score printed

## Citations & References

* Formula One Kaggle Dataset:
https://www.kaggle.com/datasets/vshreekamalesh/comprehensive-formula-1-dataset-2020-2025
* Scikit-learn documentation:
https://scikit-learn.org/

## Concluding Statement

This project demonstrates how structured motorsport data can be used to build predictive models, bridging sports analytics and machine learning while highlighting both the strengths and limitations of predictive modeling in dynamic, real-world environments.
