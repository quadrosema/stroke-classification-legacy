# Stroke Classification — Legacy Learning Project

An early machine learning exercise exploring preprocessing, class balancing, feature selection and comparison of traditional classifiers. Preserved as a record of my learning before the agent and retrieval systems featured on my [profile](https://github.com/quadrosema).

**Status: archived legacy project.** This snapshot is not maintained as a runnable or validated application.

## Intended experiment

The source explores:

- Dataset inspection and class imbalance.
- Missing-value handling, standardization and categorical encoding.
- SMOTE oversampling.
- Feature selection with Random Forest importance, SelectKBest and recursive elimination.
- Logistic Regression, Random Forest, Gradient Boosting, XGBoost and LightGBM.
- Classification reports and ROC visualizations.

## Known limitations

The current entry point has startup problems: its relative dataset path differs from the documented root invocation, and it assigns the return value of a preprocessing function that mutates the frame without returning it.

Standardization and SMOTE also occur before the train/test split in this snapshot. That allows information from the eventual test population to influence training preparation, so the resulting metrics should not be treated as an independent generalization estimate.

A corrected experiment would split the original data first, fit learned preprocessing on training data only, oversample only the training partition and evaluate on an untouched test set. These corrections are not implemented in this archived snapshot.

## Repository map

| Path | Responsibility |
| --- | --- |
| `src/read.py` | Dataset inspection |
| `src/preprocess.py` | Cleaning, encoding and scaling |
| `src/prepare.py` | Balancing, splitting and feature selection |
| `src/models.py` | Classifier comparison |
| `src/main.py` | Original entry point |

This is an educational classification exercise with no clinical validation. My current AI engineering work is presented in [Quadro](https://github.com/quadrosema/Quadro-AI-assistant), [AgentGuard](https://github.com/atrix187/AgentGuard) and the [Academic Intelligence Platform](https://github.com/quadrosema/academic-intelligence-platform).
