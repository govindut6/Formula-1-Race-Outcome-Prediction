# 🏎️ Formula 1 - Race Outcome Prediction

This repository explores predictive modeling of Formula One race outcomes using structured race data from Kaggle, using regression and classification techniques to analyze the relationship between conditions and race performance:
https://www.kaggle.com/datasets/vshreekamalesh/comprehensive-formula-1-dataset-2020-2025 

## Overview

The objective is to predict Formula One race outcomes using tabular data, analyzing how variables like grid position, constructor, and performance metrics influence finishing position. The task is framed as both regression (finishing position) and classification (top-10 finish). Using Linear Regression and a Decision Tree Classifier, results show strong classification accuracy for top-10 predictions, while regression performance reflects the complexity of race outcomes. This is barring unpredictability with collisions/failures and weather conditions.

## Summary of Workdone

### Data

* Dataset:
  * Type:
    * Input: CSV file containing race data (drivers, grid position, constructors, lap times, etc.)
    * Output: Regression: finishing position, Classification: top 10 finish
  * Size: Dataset includes multiple seasons (2020–2025). 480 rows × 16 columns

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
    * Classification: top 10
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
  * Single-pass training
* Challenges: 
  * Handling categorical variables
  * Managing missing values

### Performance Comparison

* Metrics: 
  * Regression: Mean Squared Error (MSE)
  * Classification: Accuracy
* Results:

| Model | Task | Metric | Performance |
| :--- | :---: | :---: | ---: |
| Linear Regression | Regression | MSE / RMSE / R² | MSE=37.85, RMSE=6.15, R²=-0.03 |
| Decision Tree | Classification | Accuracy | 100.0% |


### Conclusions

* Grid position is the strongest predictor of race outcome → drivers who start near the front finish near the front.
* Constructor also plays a significant role, as car performance directly affects finishing position.
* The classification model (Top-10 prediction) performs well, showing these two features are strong predictors.
* The regression model shows moderate error → Race outcomes are not predictable due to randomness (pit stops, weather, crashes).

### Future Work

* Implement a Random Forest ML model
* Include additional features such as weather conditions and pit stop strategies
* Use time-series modeling for race progression
* Perform hyperparameter tuning

## Visualizations

* (Had issues generating a proper scatter plot with my given data)
<img width="889" height="590" alt="image" src="https://github.com/user-attachments/assets/71320fc8-8c18-42e6-b740-9c3eedbbb395" />
*
<img width="1089" height="490" alt="image" src="https://github.com/user-attachments/assets/e2a8f6f2-6d78-49b5-bd8f-5f589e9c48a3" />
* 
<img width="1390" height="495" alt="image" src="https://github.com/user-attachments/assets/b46dcb0c-3989-4109-bd4d-316144144ba8" />
*
<img width="1389" height="489" alt="image" src="https://github.com/user-attachments/assets/9bb5a90b-4425-4f32-adab-bd1a4c3bec92" />
*
<img width="557" height="489" alt="image" src="https://github.com/user-attachments/assets/869cd897-60be-4e93-b8dd-0a6ff54ae190" />

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
