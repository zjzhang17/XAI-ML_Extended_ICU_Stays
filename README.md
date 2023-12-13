# XAI-ML_Extended_ICU_Stays

## Abstract:

This research paper introduces an advanced predictive model designed to forecast extended stays in the Intensive Care Unit (ICU), expanding upon prior work. The primary objectives encompass improving predictive accuracy and ensuring model transparency. The project delves into model intricacies, integrating Explainable AI (XAI) techniques. Results showcase substantial enhancements in predictive capabilities, highlighting real-world applicability for ICU deployment scenarios. The overarching goal is to refine a predictive model tailored for forecasting prolonged ICU stays, thereby contributing to efficient resource allocation, early risk identification, and informed decision-making in patient care.

## Introduction:

In modern healthcare delivery, the effective management and optimization of resources within Intensive Care Units (ICUs) are critical. The complexity of ICU care, with specialized medical and nursing interventions for critically ill patients, necessitates a well-structured framework to address challenges associated with resource constraints (1).

Despite the potential of ICU patient monitoring to reduce complications, lower mortality rates, and improve overall care quality, the demand for these resources often surpasses their availability. This incongruity results in challenges related to bed allocation, staffing shortages, and optimal equipment utilization. Healthcare institutions are compelled to find innovative solutions to balance these constraints with the growing demand for critical care services (2).

Recognizing the need for effective resource management, accurate prediction of extended Length of Stay (LOS) in ICUs has emerged as a valuable tool. Precise LOS prediction offers benefits beyond addressing challenges related to bed allocation, staffing, and equipment usage.

One significant advantage is the potential for reduced healthcare costs. Accurate LOS predictions enable healthcare providers to optimize resource allocation and implement interventions at an earlier stage, resulting in substantial cost savings. This efficiency benefits both the institution and contributes to the broader goal of delivering cost-effective patient care (3).

Furthermore, accurate LOS prediction plays a pivotal role in improving hospital bed turnover. Timely identification of patients with extended LOS allows for expedited discharge processes, freeing up beds for incoming patients. This enhancement in bed turnover addresses the immediate challenge of bed availability and contributes to the overall efficiency of healthcare facilities.

Equally significant is the positive impact accurate LOS prediction can have on patient satisfaction. Anticipating the needs of critically ill patients and providing timely interventions enhances the quality of medical services, creating a more patient-centered experience. Through proactive care planning and resource optimization, hospitals can elevate overall satisfaction levels, fostering trust in the healthcare system (4).

In essence, accurate prediction of extended LOS in ICUs goes beyond resource management; it serves as a linchpin in delivering high-quality, cost-effective patient care while simultaneously improving efficiency and satisfaction levels within critical care settings.

## Objectives:

This project aims to develop predictive models for identifying patients with extended stays in the Intensive Care Unit (ICU), leveraging the MIMIC-IV dataset.

## Methodology:

### 3.1 Data Source and Preprocessing:

Data is obtained from the Medical Information Mart for Intensive Care (MIMIC-IV dataset, version 2, obtained from the Beth Israel Deaconess Medical Center) dataset, via [https://mimic.mit.edu/](https://mimic.mit.edu/) after obtaining credentials and signing data use agreements. The dataset, capturing patients with seven or more days in the ICU, undergoes meticulous preprocessing. We utilized the provided main pipeline to extract data from the dataset, resulting in four different .csv files (demo_all, dynamic_all, labels, static_all). To simplify the data analysis process, we merged the four datasets into one using pandas merge functions (pd.merge). This merged dataset comprises 29,506 observations and 2,133 features. Categorical variables ('gender,' 'insurance,' and 'ethnicity') are transformed into numeric representations using one-hot encoding, enriching the feature set. The dataset undergoes further stratification into continuous and categorical features, paving the way for tailored preprocessing strategies.

### 3.2 Feature Engineering:

A robust feature selection process is incorporated into our methodology, empowering users to interactively choose relevant data elements. Diagnoses, procedures, medications, lab events, output events, and chart events are among the selected features, distinguishing between ICU and non-ICU scenarios. An interactive feature preprocessing module is introduced, enabling users to clean lab and chart events through outlier removal and unit conversion, ensuring model reliability and transparency. The time series data processing section provides customization options, allowing users to define the length of time-series data, specify bucket size, and implement imputation strategies for missing values. The ethnicity variable is recoded and regrouped into six groups: 'WHITE,' 'BLACK,' 'OTHER/UNKNOWN,' 'HISPANIC/LATINO,' 'ASIAN,' 'NATIVE AMERICAN.' Later, categorical variables ('gender,' 'insurance,' and 'ethnicity') are transformed into numeric representations using one-hot encoding, enriching the feature set. The dataset undergoes further stratification into continuous and categorical features, paving the way for tailored preprocessing strategies.

### 3.3 Data Splitting:

In preparation for model development, a holdout validation (train-validation-test) strategy was employed, partitioning the final dataset into an 80% training and 20% testing set. The training dataset was further partitioned into 80% training and 20% validation. With that, the whole dataset was divided into three subsets: a training set for model development, a validation set for hyperparameter tuning and model selection, and a test set held aside for the final evaluation of the trained model's performance on new, unseen data.

### 3.4 Model Selection and Building:

Due to the observed imbalanced dataset, we chose the RandomForest ML model and XGBoost Machine Learning Models. In addition to these machine learning models, we added Explainable AI (XAI) techniques. 

### 3.5 Integrated Dataset Processing:

The merged dataset undergoes a multi-step preprocessing and feature engineering pipeline, ensuring it is aptly structured for subsequent machine learning tasks. This involves specific steps such as duplicate removal, categorical transformation, dimensionality reduction visualization using t-SNE, and the construction of a `ColumnTransformer` for standardized preprocessing. This meticulous approach guarantees the dataset's suitability for training and evaluating machine learning models.

## 4. Results and Discussion:

In this project, the XGBoost algorithm was harnessed for binary classification, involving a comprehensive model development and evaluation process. A foundational XGBoost classifier was initially constructed and seamlessly integrated into a pipeline with crucial preprocessing steps. The model underwent training on the provided dataset, achieving an accuracy of 87.88% on a validation set. Subsequent meticulous analysis, including a detailed classification report and confusion matrix, laid the foundation for refining the model's predictive capabilities. Employing a hyperparameter tuning approach via GridSearchCV CV=5 further enhanced the XGBoost model, with optimal hyperparameters (learning rate of 0.2, maximum depth of 3, and 200 estimators) achieving an 88% accuracy on an independent test set. This study meticulously explores the application of the XGBoost algorithm, progressing from initial model development to hyperparameter fine-tuning, unequivocally demonstrating its effectiveness in binary classification.

The analysis section focused on understanding feature importance, utilizing the OneHotEncoder for categorical features. The OneHotEncoder, extracted from the pipeline's preprocessing steps, was specifically applied to ensure precise feature encoding. The resulting feature importances, calculated by the XGBoost model, were amalgamated with non-categorical features, generating a comprehensive list. Visualized through a horizontal bar plot, the top 50 features offer a clear

## References:

1.  	Marshall, J. C., Bosco, L., Adhikari, N. K., Connolly, B., Diaz, J. V., Dorman, T., Fowler, R. A., Meyfroidt, G., Nakagawa, S., Pelosi, P., Vincent, J. L., Vollman, K., & Zimmerman, J. (2017). What is an intensive care unit? A report of the task force of the World Federation of Societies of Intensive and Critical Care Medicine. Journal of Critical Care, 37, 270–276. https://doi.org/10.1016/j.jcrc.2016.07.015
2.  	Alghatani, K., Ammar, N., Rezgui, A., & Shaban-Nejad, A. (2021). Predicting Intensive Care Unit Length of Stay and Mortality Using Patient Vital Signs: Machine Learning Model Development and Validation. JMIR medical informatics, 9(5), e21347. https://doi.org/10.2196/21347
3.  	  Merhan A. Abd-Elrazek, Ahmed A. Eltahawi, Mohamed H. Abd Elaziz, Mohamed N. Abd-Elwhab, Predicting length of stay in hospitals intensive care unit using general admission features, Ain Shams Engineering Journal, Volume 12, Issue 4, 2021, Pages 3691-3702, ISSN 2090-4479, https://doi.org/10.1016/j.asej.2021.02.018. (https://www.sciencedirect.com/science/article/pii/S2090447921001349)
4.  	Clarke, J. L., Bourn, S., Skoufalos, A., Beck, E. H., & Castillo, D. J. (2017). An Innovative Approach to Health Care Delivery for Patients with Chronic Conditions. Population health management, 20(1), 23–30. https://doi.org/10.1089/pop.2016.0076
