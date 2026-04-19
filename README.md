# Tornado Occurrence Prediction Using Random Forest Classification

## Overview
A machine learning classifier that identifies whether a recorded severe weather event was a tornado based on geographic, temporal, and meteorological attributes. Built using 71 years of NOAA Storm Events data (1950-2021).

## How to Run

### Requirements
- Python 3.x
- Jupyter Notebook or VS Code with Jupyter extension

### Installation
1. Clone the repository
2. Download the NOAA Storm Events Database from Kaggle: https://www.kaggle.com/datasets/crawford/noaa-storm-events-database
3. Extract and place the data folder in the project directory as `noaa_data/`
4. Install dependencies: pip install pandas scikit-learn matplotlib seaborn plotly jupyter ipykernel

### Running the Notebook
1. Open `tornado.ipynb` in Jupyter or VS Code
2. Select your Python kernel
3. Run all cells in order (Cell → Run All)
4. When prompted by the prediction demo cell, enter the requested inputs

### Notes
- The `noaa_data/` folder is not included in the repository due to file size
- Training the full model takes approximately 2-3 minutes
- GridSearchCV tuning takes approximately 3-7 minutes

## Algorithm
Random Forest Classification — an ensemble method that builds 200 decision trees and combines their predictions by majority vote. Chosen for its ability to handle tabular weather data, resistance to overfitting, and interpretable feature importance scores.

## Dataset
NOAA Storm Events Database (1950-2021) — accessed via Kaggle. Contains 1.6 million records across all severe weather event types. Tornado records (72,030) were balanced against an equal number of non-tornado events via undersampling.

## Features Used
- Month, day, and time of event
- Start latitude and longitude
- State
- Direct injuries and deaths reported

## Results
| Metric | Score |
|--------|-------|
| Accuracy | 77.82% |
| Precision | 73.78% |
| Recall | 86.33% |
| F1-Score | 79.56% |
| AUC | 86.64% |
| CV Mean F1 | 74.38% |

Random Forest outperformed Gradient Boosting on 3 of 4 metrics.

## Key Findings
- Longitude and latitude are the strongest predictors — tornadoes cluster geographically in Tornado Alley
- The model performs best in winter months (January, December) and struggles most during peak tornado season (June, July)
- Tornado Alley states (Kansas, Oklahoma, Missouri, Indiana) have the lowest accuracy — the hardest region to distinguish tornado from non-tornado conditions
- The model almost never misses EF4/EF5 tornadoes (0.4% and 0.0% miss rate)

## Limitations
- No atmospheric features (pressure, wind shear, humidity) — dataset does not include pre-storm readings
- Classifies historical recorded events rather than predicting future tornado occurrence
- Model struggles in ambiguous conditions common to Tornado Alley

## Tools
Python, scikit-learn, pandas, matplotlib, seaborn, plotly