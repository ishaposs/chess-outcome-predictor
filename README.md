# Chess Game Outcome Predictor ♟️

A machine learning project that predicts the outcome of a chess game — **White Win, Black Win, or Draw** — using player ratings and game metadata from Lichess games.

---

## Overview

This project builds a complete multi-class classification pipeline on a dataset of over 20,000 chess games from Lichess. The goal was to evaluate how effectively pre-game and game metadata could predict match outcomes.

The project compares multiple machine learning models and analyzes which features contribute most to prediction performance.

---

## Dataset

Dataset used: [Chess Game Dataset (Lichess) on Kaggle](https://www.kaggle.com/datasets/datasnaek/chess)

The dataset contains:
- 20,000+ chess games
- Player Elo ratings
- Game outcomes
- Opening information
- Time controls
- Move counts and metadata

Download `games.csv` and place it in the project root before running the project.

---

## Target Classes

The model predicts one of three possible outcomes:
- White Win
- Black Win
- Draw

---

## Features Used

Key features included:
- White player rating
- Black player rating
- Rating difference
- Absolute rating difference
- Rated vs casual game
- Time control base + increment
- Opening ECO code
- Opening name
- Number of turns

---

## What I Did

- Cleaned and preprocessed the dataset
- Removed irrelevant columns such as usernames, timestamps, and raw move lists
- Engineered new features from player ratings and time controls
- Built a full preprocessing pipeline using:
  - Imputation
  - Standard scaling
  - One-hot encoding
- Trained and compared multiple machine learning models:
  - Linear SVM
  - Random Forest
  - Gradient Boosting
  - XGBoost

---

## Model Performance

| Model | Accuracy |
|---|---|
| Linear SVM | 65.8% |
| Gradient Boosting | 69.0% |
| Random Forest | 68–70% |
| **XGBoost** | **89.5%** |

XGBoost achieved the best overall performance.

The strongest predictor was the rating difference between players, which aligns with the intuition that games become more predictable as the skill gap increases.

The most difficult class to predict was draws, mainly because they are relatively rare in the dataset.

---

## Tech Stack

- Python
- pandas
- scikit-learn
- XGBoost
- matplotlib
- seaborn

---

## Project Structure

```text
├── ml_minproject.ipynb
├── games.csv
├── requirements.txt
└── README.md
```

---

## How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Download `games.csv` from Kaggle and place it in the project root.

---

## Future Improvements

- Handle class imbalance more effectively
- Tune hyperparameters using GridSearchCV or Optuna
- Add cross-validation metrics
- Deploy the model using Flask or Streamlit
- Experiment with deep learning approaches

---

## Key Learning Outcomes

Through this project, I learned:
- Feature engineering for structured datasets
- Building reusable sklearn pipelines
- Multi-class classification techniques
- Model comparison and evaluation
- Interpreting feature importance in ensemble models

---

## Acknowledgements

Dataset provided by [Kaggle](https://www.kaggle.com/) and sourced from Lichess game data.
