# Performance Metrics for Classification

This notebook provides an interactive introduction to **performance metrics used in evaluating classification models**. It is adapted from Aurélien Géron's Chapter 3 notebook under the Apache v2 License.

## Purpose

The focus is on **evaluating classifiers**, not on training them. Students will explore key metrics used to assess classification performance, such as:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- ROC Curve and AUC

## Learning Format

This notebook is designed for **active learning** in a classroom setting. Students are encouraged to:

- Run code cells during instruction
- Respond to questions marked "_To the student_" in new cells
- Take notes and annotate the notebook
- Commit and push their personalized version to their own repository

## What is Classification?

Classification is a supervised learning task where the goal is to assign input data to one of several predefined categories. A **classifier** is an algorithm or function that performs this mapping from input features to class labels.

Examples include:
- Email spam detection
- Medical diagnosis
- Image recognition

For more background, see the Wikipedia article on classification and classification algorithms.


## Our Workshop Results

We completed all 13 “To the student” sections, including the
Fashion-MNIST exercise, security drone calculations, and manual
recall and F1 calculations.

### MNIST: Detecting the Digit 5

We evaluated models using three-fold cross-validation on the
60,000 training images.

| Metric | SGDClassifier | Random Forest |
|---|---:|---:|
| Precision | 83.71% | 98.97% |
| Recall | 65.12% | 87.25% |
| F1-score | 0.7325 | 0.9275 |
| ROC AUC | 0.9605 | 0.9983 |

These results use a decision threshold of zero for SGD and a
probability threshold of at least 0.5 for Random Forest.

Random Forest achieved higher precision and recall, detecting
more actual 5s while producing fewer false alarms.

### Fashion-MNIST: Detecting Sandals

We repeated the workflow using label '5', which represents sandals.

- SGD mean cross-validation accuracy: **97.492%**
- Dummy baseline accuracy: **90.000%**

## Key Insights

- **Accuracy alone can mislead.** The MNIST dummy classifier
  achieved 90.965% accuracy by always predicting “not 5,”
  missing every actual 5.
- **Confusion matrices explain errors.** They distinguish
  false positives from false negatives.
- **Precision and recall answer different questions.**
  Precision measures the correctness of positive predictions;
  recall measures how many actual positives are detected.
- **F1 combines precision and recall.** A high F1 requires
  both metrics to be high.
- **Thresholds affect the tradeoff.** Raising the SGD threshold
  to approximately 3370.02 produced 90.003% precision but
  reduced recall to approximately 48.00%.
- **Metric choice depends on the task.** We should consider
  the relative costs of false alarms and missed positives.
- **ROC AUC is not accuracy.** It summarizes how well scores
  rank positive examples above negative examples.
- **Estimated probabilities may need calibration.** In the
  Random Forest group assigned 50%–60% probability of being
  a 5, 94% of images were actually 5s.

## Evaluation Scope

The reported model metrics come from cross-validation on the
training data. The separate 10,000-image test sets were not used
to calculate these metrics. A threshold selected to achieve
90% precision on these validation predictions does not guarantee
90% precision on new data.

## Notebook

Open `PerformanceMetricsClassification.ipynb` to see the executed
code, visualizations, student responses, and final summary.

## Acknowledgements

- [Instructor's workshop repository](https://github.com/ProfEspinosaAIML/PerformanceMetricsClassification)
- [Aurélien Géron's original Chapter 3 notebook](https://github.com/ageron/handson-ml3/blob/main/03_classification.ipynb)
- [Fashion-MNIST dataset](https://github.com/zalandoresearch/fashion-mnist)

The workshop notebook retains its original attribution to
Aurélien Géron's work under the Apache 2.0 License.

