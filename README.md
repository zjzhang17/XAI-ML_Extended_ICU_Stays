# XAI-ML_Extended_ICU_Stays

## Abstract:

This research presents an advanced predictive model for forecasting prolonged stays in the Intensive Care Unit (ICU). Objectives include improving predictive accuracy and ensuring model transparency through Explainable AI (XAI) techniques. Results exhibit substantial enhancements in predictive capabilities, emphasizing real-world applicability for ICU scenarios. The project aims to refine a predictive model for prolonged ICU stays, contributing to efficient resource allocation and informed decision-making in patient care.

## Introduction:

In modern healthcare, effective management of Intensive Care Units (ICUs) is crucial due to the complex nature of care for critically ill patients. Despite the potential benefits of ICU monitoring, resource demand often exceeds availability, leading to challenges in resource allocation. Accurate prediction of extended Length of Stay (LOS) in ICUs is essential for reducing healthcare costs, improving bed turnover, and enhancing patient satisfaction. This project focuses on developing predictive models for extended ICU stays using the MIMIC-IV dataset, contributing to improved healthcare methodologies.

## Objectives:

Develop predictive models for identifying patients with extended stays in the ICU using the MIMIC-IV dataset.

## Methodology:

1. Data Source and Preprocessing:**
   - Utilized the MIMIC-IV dataset obtained from [https://mimic.mit.edu/](https://mimic.mit.edu/).
   - Meticulous preprocessing, merging four datasets into one, resulting in 29,506 observations and 2,133 features.
   - Categorical variables transformed using one-hot encoding, and further stratification into continuous and categorical features.

2. Feature Engineering:**
   - Selected relevant features, distinguishing between ICU and non-ICU scenarios.
   - Introduced interactive feature preprocessing for data cleaning and transparency.
   - Recoded and regrouped the ethnicity variable.
   - Stratified dataset into continuous and categorical features.

3. Data Splitting:
   - Employed a holdout validation strategy (train-validation-test) with an 80% training and 20% testing set.
   - Further partitioned the training dataset for model development and hyperparameter tuning.
   - Dataset divided into subsets for training, validation, and final evaluation.

4. Model Selection and Building:
   - Chose RandomForest ML model and XGBoost Machine Learning Models due to an imbalanced dataset.
   - Integrated Explainable AI (XAI) techniques.

5. Integrated Dataset Processing:
Employed a multi-step preprocessing and feature engineering pipeline.
Ensured dataset suitability for training and evaluating machine learning models.

## Results and Discussion:

Utilized XGBoost for binary classification, achieving 87.88% accuracy on the validation set.
Hyperparameter tuning enhanced the XGBoost model to 88% accuracy on an independent test set.
Explored feature importance, visualized through a horizontal bar plot, offering insights into model performance.

This project demonstrates the effectiveness of the XGBoost algorithm in predicting prolonged ICU stays and contributes to improved healthcare practices.

## References:

1.  	Marshall, J. C., Bosco, L., Adhikari, N. K., Connolly, B., Diaz, J. V., Dorman, T., Fowler, R. A., Meyfroidt, G., Nakagawa, S., Pelosi, P., Vincent, J. L., Vollman, K., & Zimmerman, J. (2017). What is an intensive care unit? A report of the task force of the World Federation of Societies of Intensive and Critical Care Medicine. Journal of critical care, 37, 270–276. https://doi.org/10.1016/j.jcrc.2016.07.015
2.  	Alghatani, K., Ammar, N., Rezgui, A., & Shaban-Nejad, A. (2021). Predicting Intensive Care Unit Length of Stay and Mortality Using Patient Vital Signs: Machine Learning Model Development and Validation. JMIR medical informatics, 9(5), e21347. https://doi.org/10.2196/21347
3.  	  Merhan A. Abd-Elrazek, Ahmed A. Eltahawi, Mohamed H. Abd Elaziz, Mohamed N. Abd-Elwhab, Predicting length of stay in hospitals intensive care unit using general admission features, Ain Shams Engineering Journal, Volume 12, Issue 4, 2021, Pages 3691-3702, ISSN 2090-4479, https://doi.org/10.1016/j.asej.2021.02.018. (https://www.sciencedirect.com/science/article/pii/S2090447921001349)
4.  	Clarke, J. L., Bourn, S., Skoufalos, A., Beck, E. H., & Castillo, D. J. (2017). An Innovative Approach to Health Care Delivery for Patients with Chronic Conditions. Population health management, 20(1), 23–30. https://doi.org/10.1089/pop.2016.0076
