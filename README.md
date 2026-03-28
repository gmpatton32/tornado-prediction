# Tornado Occurrence Prediction Using Random Forest Classification

## Overview
A machine learning classifier that identifies whether a recorded severe weather event was a tornado based on geographic, temporal, and meteorological attributes. Built using 71 years of NOAA Storm Events data (1950-2021).

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
- The model performs best in off-peak months (February, April) and struggles most during peak tornado season (May, June)
- Tornado Alley states (Kansas, Oklahoma, Missouri) have the lowest accuracy — the hardest region to distinguish tornado from non-tornado conditions
- The model almost never misses EF4/EF5 tornadoes (0.4% and 0.0% miss rate)

## Limitations
- No atmospheric features (pressure, wind shear, humidity) — dataset does not include pre-storm readings
- Classifies historical recorded events rather than predicting future tornado occurrence
- Model struggles in ambiguous conditions common to Tornado Alley

## Tools
Python, scikit-learn, pandas, matplotlib, seaborn, plotly
