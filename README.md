
````markdown
# Microbiota Status Classification

## Project Overview
This project develops a transformer-based machine learning model to classify patients' gut microbiota status into categories such as "Optimal" and "Not Optimal" using health indicators, medical history, dietary habits, and lifestyle factors. The goal is to build accurate, interpretable models that can assist in understanding and predicting gut microbiota health status from non-invasive data.

The project explores baseline classical models (Logistic Regression, Random Forest, XGBoost, LightGBM), advanced neural network architectures including an Artificial Neural Network (ANN), and state-of-the-art transformer-based models like TabTransformer. Model evaluation includes multiple metrics and visualization tools to interpret performance and feature importance.

---

## Dataset Description
The dataset comprises patient health records with key feature categories:

- **Demographics:** Height, Weight, BMI  
- **Medical History:** Diagnosed conditions (e.g., Diabetes, Hypertension), Surgeries, Family history  
- **Lifestyle:** Physical activity type, Sleep hours, Stress level, Smoking status  
- **Diet:** Weekly consumption of vegetables, fruits, proteins (plant and animal), fermented foods, water, alcohol  
- **Gastrointestinal Health:** Frequency of bowel movements, Stool consistency, Bloating, Gas, Abdominal pain  
- **Target Variable:** Current microbiota status labeled as Optimal, Suboptimal, or At Risk

The dataset contains approximately 10,000 patient records with both numerical and categorical features, some requiring preprocessing and feature engineering for effective modeling.

---

## Setup Instructions

1. **Clone the repository** (if applicable) or download the project files.

2. **Environment Setup:**

   Use Python 3.8+ with the following packages:

   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn
   pip install xgboost lightgbm optuna
   pip install torch torchvision torchaudio  # For ANN and transformer models
   pip install pytorch-tabular pytorch-lightning
   pip install shap
````

3. **Data Preparation:**

   * Place your dataset CSV file in the project directory.
   * Run preprocessing scripts to clean, encode, and engineer features.

4. **Run Model Training:**

   * Execute the provided Jupyter notebooks or Python scripts.
   * Baseline models (Logistic Regression, Random Forest, XGBoost) can be trained first.
   * For transformer models, ensure GPU acceleration is enabled for best performance.

5. **Model Evaluation and Interpretation:**

   * View accuracy, precision, recall, F1-score, ROC AUC metrics.
   * Generate confusion matrices and ROC curves.
   * Use SHAP or feature importance plots for interpretability.

---

## Key Results

* **Baseline Models:**

  * Logistic Regression achieved \~52% accuracy, near random baseline.
  * Random Forest and XGBoost showed overfitting with high training but low test accuracy (\~49-50%).
* **Advanced Models:**

  * LightGBM and ANN models showed incremental improvements but limited by dataset features.
  * Hyperparameter tuning with Optuna improved XGBoost performance moderately.
* **Transformer-Based Model (TabTransformer):**

  * Demonstrated promising ability to model complex feature interactions.
  * Provided better F1-scores and ROC AUC metrics compared to classical models.
* **Feature Importance:**

  * Gut-related features such as symptom scores, plant-to-animal protein ratio, and fiber intake were among the top contributors.
  * Lifestyle and diet variables also played important roles in predictions.

---

## Notes

* Achieving very high accuracy (>80%) is challenging due to inherent overlap and noise in the target labels and features.
* Future work includes integrating microbiome sequencing data and other biomarkers for improved prediction.
* Model explainability remains a focus to ensure clinical relevance and trustworthiness.

--
