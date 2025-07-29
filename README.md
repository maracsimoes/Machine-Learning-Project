# Workers Compensation Claim Injury Type Prediction

## Abstract  
This project addresses the challenge faced by the New York Workers’ Compensation Board (WCB) to automate the decision-making process for workers’ compensation claims. Using claim data from 2020 to 2022, we developed machine learning models to predict the **type of injury** associated with each claim. We evaluated several classification algorithms, optimized the best-performing models, and explored additional insights, including feature importance and predicting related variables such as agreement status. Our findings demonstrate that tree-based ensemble methods like XGBoost offer strong predictive performance, and incorporating additional variables may further improve accuracy. This work aims to streamline WCB’s claim handling and reduce manual workload.

## Project Overview  
The New York WCB regulates workers’ compensation claims and processes over 5 million claims since 2000. Manual claim review is resource-intensive, motivating the use of machine learning for automating injury type classification. This project has three main goals:

1. **Multiclass Classification Benchmarking**  
   Build and compare models to predict the WCB’s final injury type decision using claims data.

2. **Model Optimization**  
   Improve selected models via hyperparameter tuning and feature selection.

3. **Additional Insights**  
   Analyze feature importance, develop models for related targets (e.g., agreement reached), and evaluate if including these improves prediction.

---

## Data  
- **Training set:** Claims from 2020 to 2022, including features and ground truth injury types.  
- **Test set:** Claims from 2023 onward, without target labels, used for final model evaluation on Kaggle.  
- Features include demographics, injury details, dates, and other claim-specific data.  

---

## Methodology

### Data Exploration and Preprocessing  
- Initial data cleaning involved handling missing values using domain-informed imputation strategies.  
- Feature engineering introduced new variables such as accident severity scores and binned numeric features.  
- Encoding techniques balanced information retention with dimensionality reduction, using binary and frequency encoding.  
- Skewness and outliers were treated using transformations and Winsorization.

### Feature Selection  
- Filter methods (correlation, ANOVA, mutual information) removed redundant features.  
- Embedded methods leveraging feature importances from models like Random Forest and XGBoost finalized the feature set.

### Model Development  
- Candidate algorithms included Decision Trees, Random Forests, XGBoost, LightGBM, Gaussian Naïve Bayes, and Neural Networks. 
- Models were assessed primarily using weighted F1 to handle class imbalance.  
- The top-performing models were fine-tuned by adjusting their hyperparameters to improve performance.
  
### Additional Insights  
- Created a secondary model to predict “Agreement Reached” without WCB intervention.  
- Tested whether including this variable as a feature improves injury type classification.  
- Conducted feature importance analysis to interpret model decisions.

---

## Evaluation Metrics  
- **Weighted F1 Score:** Measures overall model performance weighted by class frequency.  
- **Confusion Matrix:** Class-level accuracy insights.  
- **Training Time:** Computational cost assessment.

---

## Results Summary  
- Tree-based ensemble methods, especially XGBoost, achieved the best balance of accuracy and efficiency.  
- Hyperparameter tuning further improved model metrics.
- Adding agreement status prediction helped improve the model in some cases, but the effect was not consistent.
