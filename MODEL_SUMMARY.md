# Model Summary

## Task

Predict the sentiment (`negative`, `neutral`, or `positive`) of a US airline
passenger tweet from its text.

## Data and validation

- 14,640 tweets across six airlines.
- Target distribution: 9,178 negative, 3,099 neutral, and 2,363 positive.
- Stratified 80/20 train/test split with `random_state=42`:
  11,712 training rows and 2,928 test rows.
- TF-IDF features use unigrams and bigrams, `min_df=2`, and sublinear term
  frequency.
- The comparison evaluates clean, stemmed, and lemmatized text variants.
- Metrics are accuracy and macro-F1. Macro-F1 gives each sentiment class equal
  weight despite the class imbalance.

## Compared classifiers

- Majority-class dummy baseline.
- Multinomial Naive Bayes (`alpha=0.3`).
- Logistic Regression (`C=3`, balanced class weights).
- Linear Support Vector Classifier (`C=0.5`, balanced class weights).
- Random Forest (200 trees, balanced subsample weights).

Each classifier is wrapped in a scikit-learn pipeline, so TF-IDF is fitted on
the training portion only.

## Recorded results

The following values come from the notebook's saved comparison output; they
have not been rerun as part of preparing this repository.

### Accuracy

| Classifier | Clean | Lemmatized | Stemmed |
|---|---:|---:|---:|
| Majority-class baseline | 0.627 | 0.627 | 0.627 |
| Naive Bayes | 0.758 | 0.756 | 0.758 |
| Logistic Regression | 0.796 | 0.781 | 0.785 |
| Linear SVM | **0.807** | 0.794 | 0.791 |
| Random Forest | 0.778 | 0.791 | 0.795 |

### Macro-F1

| Classifier | Clean | Lemmatized | Stemmed |
|---|---:|---:|---:|
| Majority-class baseline | 0.257 | 0.257 | 0.257 |
| Naive Bayes | 0.637 | 0.634 | 0.638 |
| Logistic Regression | 0.742 | 0.726 | 0.731 |
| Linear SVM | **0.745** | 0.729 | 0.726 |
| Random Forest | 0.686 | 0.717 | 0.724 |

The best recorded setting is the clean-text Linear SVM (accuracy 0.807,
macro-F1 0.745). The improvement over the dummy model's macro-F1 (0.257)
shows that the model learns signal beyond always selecting the majority
class.

## Limitations

- The dataset is imbalanced and may not represent current passenger language
  or airline populations.
- A random held-out split is not a time-based or airline-based generalization
  test.
- Scores are cached notebook output, not a fresh run in the current
  environment.
- The notebook does not persist a fitted model or provide production
  monitoring; results should not be treated as a deployed service.
