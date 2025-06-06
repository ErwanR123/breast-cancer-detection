#  🩺 Early Breast Cancer Detection using Blood Biomarkers

**Université Paris Dauphine - PSL**  
Statistical Learning Project — Academic Year 2024–2025  
**Supervisors:** Prof. Gabriel Turinici, Dr. Laetitia Comminges  

## Project Objective

The goal of this project is to predict the presence of breast cancer using blood-based biomarkers. Several supervised classification models are compared, with a strong focus on **recall** to reflect the clinical need to minimize false negatives (i.e., undiagnosed patients).

## Dataset

- **Source:** Breast Cancer Coimbra Dataset (116 patients, 9 biomarkers)
- **Target variable:** `Classification` (0 = healthy, 1 = cancer)
- **Preprocessing steps:**
  - Logarithmic transformation of skewed variables
  - Standardization (Z-score)
  - Stratified train/test split (92/24)

## Models Compared

| Model                        | Recall | F1-score | AUC   |
|-----------------------------|--------|----------|-------|
| k-Nearest Neighbors (k=23)  | 0.92   | 0.788    | 0.88  |
| Neural Network (MLP)        | 0.92   | 0.69     | 0.83  |
| Logistic Regression (L2)    | 0.69   | 0.75     | 0.79  |
| Gaussian Naïve Bayes        | 0.58   | 0.68     | 0.72  |

**Best model for clinical usage (recall priority):** k-NN (k = 23)

## Repository Structure

- `eda_analysis.ipynb` – Data exploration, visualization, and preprocessing
- `logistic_regression.ipynb` – Logistic regression (basic and optimized via GridSearchCV)
- `knn.ipynb` – k-Nearest Neighbors with cross-validation and performance tuning
- `neural_network.ipynb` – Feedforward neural network (MLPClassifier)
- `naive_bayes.ipynb` – Gaussian Naïve Bayes with log-transformed inputs
- `svm.ipynb` – Preliminary experiments with SVM (bonus, not included in the final report)
- `Subject_3_Ouabdesselam_Forest_Durousseau_Danjou_vonSiemens.pdf` – Final report (comprehensive analysis and conclusions)
- `README.md` – This file

## Evaluation Metrics

- **Recall:** prioritized (to avoid false negatives)
- **F1-score:** balances precision and recall
- **ROC & AUC:** overall discriminative ability

## Clinical Recommendation

Assuming false positives are acceptable to avoid missing cancer cases, the k-NN (k = 23) model is preferred. It offers the best compromise between recall and F1-score, and reliably identifies patients at risk.

## Authors

Erwan Ouabdesselam  
Antonin Durousseau  
Moritz von Siemens  
Arthur Danjou  
Thaïs Forest

---

Project completed as part of the Statistical Learning course in the Master’s program in Applied Mathematics at Université Paris Dauphine - PSL.
