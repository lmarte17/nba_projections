# Predicting Fantasy Basketball Player Value Performance

## Project Overview

This project focuses on predicting the value performance of NBA players in daily fantasy basketball. Traditional methods often predict raw fantasy points, but this project shifts the focus towards predicting **value performance**—a more nuanced metric that represents the efficiency of a player relative to their salary. The goal is to optimize player selection within a salary cap, ensuring that the lineup is both cost-effective and competitive.

## Problem Statement

In daily fantasy basketball, simply predicting raw fantasy points can lead to suboptimal lineup choices. The real challenge lies in selecting players who provide the best value for their salary. This project aims to predict value performance, defined as the ratio of fantasy points to salary, to help fantasy sports enthusiasts make more strategic decisions.

## Significance

Prioritizing value performance over traditional fantasy points allows for a more strategic allocation of the fantasy budget, leading to better-balanced and more competitive lineups. This approach is critical in daily fantasy sports, where budget constraints are a key factor in lineup optimization.

## The Dataset

The dataset was compiled from several sources:

- [NBA.com/stats](https://www.nba.com/stats): For team and player statistics.
- [SportsData.io](https://sportsdata.io): For schedules.
- [SaberSim](https://sabersim.com): For projected minutes, ownership, and salary.

### Key Features

1. **Player Information:**
   - Name, Position, Team, Opponent.

2. **Game-Specific Data:**
   - Date, Salary, Ownership, Projected Minutes.

3. **Historical Performance Metrics:**
   - Metrics over different time frames (e.g., season-long, last 10 games).

4. **Efficiency Metrics:**
   - Fantasy Points per Minute, Touch, Possession.

5. **Team-Related Metrics:**
   - Team Fantasy Points, Salary, Ownership, Projected Minutes.

6. **Player's Team Impact:**
   - Salary Share, Percentage of Team's Possessions, Fantasy Points Scored.

7. **Projections:**
   - Projected Fantasy Points, Value.

8. **Actual Results:**
   - Actual Fantasy Points, Value.

## Machine Learning Approaches

### Models Used

1. **Logistic Regression:**
   - Baseline model for simplicity and interpretability.
2. **Random Forest Classifier:**
   - An ensemble learning method to improve predictive accuracy.
3. **XGBoost Classifier:**
   - A powerful gradient boosting algorithm known for high performance.
4. **Support Vector Machine (SVM):**
   - A classifier that optimally separates classes with a hyperplane.

### Hyperparameter Tuning

`GridSearchCV` was used to optimize the hyperparameters for each model. The models were evaluated based on accuracy, precision, recall, and F1-score, with parallel processing enabled via `n_jobs=-1` for efficient computation.

## Results and Analysis

### Logistic Regression
- **Accuracy:** 56.73%
- **Strengths:** Balanced recall and precision for both classes.
- **Weaknesses:** Moderate overall accuracy, with potential over-prediction of positive cases.

### Random Forest Classifier
- **Accuracy:** 56.81%
- **Strengths:** Good at capturing complex patterns.
- **Weaknesses:** Struggled with predicting high-value players (class 1).

### XGBoost Classifier
- **Accuracy:** 56.89%
- **Strengths:** Balanced performance, robust and flexible.
- **Weaknesses:** Similar issues with class 1 predictions as Random Forest.

### Support Vector Machine (SVM)
- **Accuracy:** 64.70%
- **Strengths:** High accuracy and perfect recall for class 0.
- **Weaknesses:** Poor performance in predicting class 1, leading to low recall.

## Decision

After evaluating all models, **Logistic Regression** was selected as the best model for our use case due to its balanced performance across both classes. While SVM showed the highest accuracy, its poor recall for class 1 made it less suitable for predicting high-value players.

## Future Possibilities

1. **Model Combination:** Explore stacking or voting classifiers to combine the strengths of multiple models.
2. **Advanced Feature Engineering:** Introduce new features or transform existing ones for improved accuracy.
3. **Hyperparameter Tuning:** Further refine hyperparameters to enhance model performance.
4. **Real-Time Predictions:** Implement the model in a real-time setting for immediate value in fantasy sports.

## How to Run the Project

### Prerequisites

- Python 3.9 or higher
- Required libraries: `scikit-learn`, `xgboost`, `pandas`, `numpy`, `matplotlib`, `seaborn`

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/lmarte/nba_projections.git
   cd nba_projections
   ```

2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Conclusion

This project demonstrates the importance of focusing on value performance in fantasy basketball, offering a more strategic approach to lineup optimization. By shifting from raw fantasy points to value, we enable more effective decision-making within the constraints of a salary cap.



