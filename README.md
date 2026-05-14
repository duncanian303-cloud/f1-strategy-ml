# F1 Strategy & Pit Stop Analysis Project

## Project Overview
This project analyzes a Formula 1 strategy dataset containing over 100,000 lap records. The goal is to understand the factors driving pit stop decisions and to build a predictive model for race strategy.

## Dataset Description
- **Source**: `f1_strategy_dataset_v4.csv`
- **Key Features**: Driver, LapNumber, Compound, Stint, TyreLife, Position, LapTime (s), Race, and Cumulative Degradation.
- **Target Variable**: `PitNextLap` (Predicting if a driver will pit on the subsequent lap).

## Key Workflow & Findings
### 1. Data Cleaning & Outlier Removal
- Identified extreme right-skewness in lap times (skewness score of ~59.4).
- Applied the Interquartile Range (IQR) method to filter out outliers (laps > 125.36s), removing approximately 2.89% of the data.

### 2. Exploratory Data Analysis (EDA)
- **Compound Performance**: Dry compounds (Hard, Medium, Soft) average ~92s per lap, whereas wet-weather tires exceed 102s.
- **Correlations**: Removing outliers clarified the relationship between `RaceProgress` and improved lap times due to fuel burn.

### 3. Predictive Modeling
- **Algorithm**: Random Forest Classifier.
- **Performance**: Achieved **94% accuracy** in predicting pit stops.
- **Feature Importance**: `Cumulative_Degradation` and `TyreLife` were the primary drivers of pit stop strategy.

### 4. Driver Deep-Dive (Max Verstappen)
- Verstappen typically pits after approximately **17.91 laps** on a set of tyres.
- Analysis showed high consistency in lap times within each stint.
