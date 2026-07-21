# Breast Cancer Classification — Logistic Regression vs. Random Forest

Binary classification of breast tumors (malignant/benign) using features extracted from digitized fine-needle aspirate (FNA) images. Built as part of my data science portfolio, mirroring the type of clinical/molecular classification work done in my MBA capstone project, using fully public data instead of research-related data.

## Data Source

- Dataset: Breast Cancer Wisconsin (Diagnostic), loaded via scikit-learn (sklearn.datasets.load_breast_cancer)
- Citation: Wolberg, W., Mangasarian, O., Street, N., & Street, W. (1993). Breast Cancer Wisconsin (Diagnostic) [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5DW2B
- License: CC BY 4.0
- Content: 569 samples, 30 numeric features per sample (size, texture, and shape measurements of cell nuclei), binary target (malignant/benign)

## Tools

- Python (Pandas, scikit-learn, Matplotlib)
- Google Colab

## Workflow

1. Load data, check class balance and missing values
2. Train/test split (80/20, stratified)
3. Feature scaling (StandardScaler)
4. Train baseline model (Logistic Regression) and compare with Random Forest
5. Evaluate with accuracy, precision, recall, F1-score, confusion matrix
6. Feature importance analysis (Random Forest)
7. 5-fold cross-validation to check result stability
8. ROC curve and AUC score

## Results

- Logistic Regression: 98.2% test accuracy, 98.1% cross-validated accuracy (± 0.7%)
- Random Forest: 95.6% test accuracy, 95.8% cross-validated accuracy (± 2.4%)
- AUC: 0.995
- Only 2 misclassifications out of 114 test samples with logistic regression (1 false positive, 1 false negative)
- Top predictive features (Random Forest): worst perimeter, worst area, worst concave points — consistent with clinical expectation that larger, more irregular cell nuclei indicate malignancy
- Logistic regression outperformed and was more consistent than Random Forest, suggesting the classes are close to linearly separable — a good example of not over-engineering when a simpler model already performs well

## Structure

notebooks/
  classification_breast_cancer.ipynb
results/
  confusion_matrix_logreg.png
  feature_importance_rf.png
  roc_curve.png

## Skills Demonstrated

- Binary classification with model comparison (linear vs. ensemble methods)
- Proper train/test methodology (avoiding data leakage in scaling)
- Cross-validation for robust model evaluation
- Threshold-independent evaluation (ROC/AUC)
- Feature importance interpretation validated against domain knowledge
- Clear reasoning for final model choice

## Status

Complete
