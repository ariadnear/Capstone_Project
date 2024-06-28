## Detecting Healthcare Fraud: Machine Learning Approaches for Medicare Insurance Claims

Authors: Ariadne Aizprua & Connie Cabrera

### Abstract
This project addresses the critical issue of Medicare claim fraud by employing advanced machine learning techniques to detect fraudulent activities. Utilizing a quantitative research design, the study relied on Borderline Synthetic Minority Over-Sampling Technique (SMOTE) to balance the dataset and applied three supervised learning techniques: LightGBM (Gradient Boosting Machine), XGBoost, and Random Forest. Feature selection was conducted using Recursive Feature Elimination (RFE) and correlation techniques to remove or exclude irrelevant variables. The top 5 crucial features for fraud detection identified from this dataset include State, County, Age, Total Deductible Amount, and Total Reimbursed Amount. The LightGBM model demonstrated the highest performance with an accuracy of 0.81, precision of 0.83, recall of 0.77, F1 score of 0.80, and AUC-ROC score of 0.81. XGBoost also presented strong results, while Random Forest had lower recall. Despite ethical consideration and the limitations of synthetic data, the findings highlight the potential of machine learning to improve fraud detection in Medicare claims, underscoring the need for further research in this area.

### Introduction
Healthcare fraud, particularly in Medicare claims, poses a significant challenge to the integrity and sustainability of healthcare systems worldwide. According to the U.S. Government Accountability Office (GAO), improper payments in the Medicare program amounted to approximately $51 billion in fiscal year 2023. This includes fraudulent payments, errors, and undocumented payments ((Medicare and Medicaid: Additional Actions Needed to Enhance Program Integrity and Save Billions, n.d.). Detecting fraud in Medicare claims is complex due to numerous factors such as the evolving nature of fraudulent schemes and the sheer volume of claims processed. Medicare fraud is a subset of healthcare fraud which specifically refers to fraudulent activities involving the Medicare program, which is a federal health insurance program primarily for people aged 65 and older, as well as certain younger individuals with disabilities.

According to the Federal Bureau of Investigations (FBI), fraudulent activities by medical providers within the Medicare program involve various deceptive practices aimed at unlawfully acquiring benefits or payments. These include submitting multiple claims for the same service (double billing), billing for services or supplies never received by the patient (phantom billing), submitting multiple bills for the same service (unbundling), and charging for a higher-cost service than provided (upcoding).
These illicit activities aim to defraud insurance companies, government healthcare programs, or patients (Health Care Fraud, 2022). To combat this issue, laws and regulations are in place to prevent and detect Medicare fraud in the United States. However, detecting fraudulent claims remains challenging, necessitating innovative approaches such as data analysis and machine learning. This project aims to address this challenge by employing exploratory data analysis (EDA) and predictive modeling to identify fraudulent patterns and improve detection accuracy.

### Objectives
The project's primary focus is using exploratory data analysis (EDA) to find suspicious patterns in healthcare insurance data. From there, the goal is to create precise machine learning models that use advanced algorithms to minimize errors and improve efficacy to differentiate between legitimate and fraudulent claims. Ongoing improvements are made with the intention of increasing the accuracy of detection by utilizing strict data preprocessing and adaptive analytics methods to predict changing fraud tactics in the healthcare industry and strengthen security against illegal activity.

### Limitations
This project uses synthetic healthcare data to develop and evaluate fraud detection algorithms under controlled conditions. Furthermore, we recognize it has limitations in terms of representing real-world complexity and ethical considerations but emphasizes its usefulness in identifying fraudulent Medicare claims with careful consideration of application scope.

### Data Collection
#### Data Source and Details
This study explores healthcare fraud claims using the “Healthcare Provider Fraud Detection" dataset obtained from Kaggle.com. The dataset, curated by Rohit Anand Gupta, offers comprehensive information on Medicare Claims sourced from the Centers for Medicare & Medicaid Services (CMS). Named “Medicare Date Entrepreneurs’ Synthetic”, it consists of synthesized data representing 5% random sample of Medicare beneficiaries in 2008 and their claims from 2008 to 2009. The original data experienced significant modifications to protect beneficiary privacy and minimize re-identification risks, while maintaining the general structure of the original Medicare beneficiary file. However, due to these alterations, findings cannot be directly extrapolated to the actual Medicare population.

The data includes four main datasets.

<img width="1335" alt="Screenshot 2024-06-28 at 12 08 51 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/a5955e35-919a-49ce-b805-8fe51fa60574">

#### Data Cleaning and Preprocessing
The data cleaning and preprocessing phase involved several crucial steps to ensure high- quality data for analysis.

<img width="1323" alt="Screenshot 2024-06-28 at 12 11 39 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/886913cf-cacc-465e-8225-16118d41788b">

### Exploratory Data Analysis

Frequency analysis revealed racial and gender disparities, with older beneficiaries (84% are white) and more women (58%) using healthcare services more frequently.
<img width="1024" alt="Screenshot 2024-06-28 at 12 12 06 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/992df65f-db9d-425b-bab7-0570e174725f">

The following picture shows in the first graph the imbalance that resulted from the provider analysis, which separated legitimate from potentially fraudulent billing patterns. Of the providers identified, 62% were found to be fraudulent, while 38% were found to be non-fraudulent. In the second graph, we see that fraud providers are related to higher reimbursement amounts. The third graph shows providers with an unusual number of claims.
<img width="1023" alt="Screenshot 2024-06-28 at 12 12 21 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/fb26d1e2-b112-4a3a-a39d-24950692488c">

The following group of violin plots illustrate the claims analysis's discovery of extreme outliers, in the number of deductibles paid, which suggested the possibility of fraudulent billing practices.
<img width="1017" alt="Screenshot 2024-06-28 at 12 12 31 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/eea5499d-de80-47c9-8880-99e81ff1c9e6">

The geographic analysis presented in the following visualization revealed fraud hotspots, particularly in densely populated states such as California, Florida, and New York, where a convergence of varied regulations and crowded cities create an environment conducive to fraud. 
<img width="1018" alt="Screenshot 2024-06-28 at 12 12 39 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/845bee1e-caa8-4f18-a1c2-6adfbd409bd9">

### Methodology
This study employs a quantitative research design using predictive modeling techniques to detect fraudulent Medicare claims. It focuses on analyzing claims to identify fraud patterns, employing machine learning techniques like supervised algorithms and feature selection to improve model accuracy. The methodology includes data preparation, feature selection, model development, and evaluation, detailed as follows:

#### Data Preparation
The initial phase involved cleaning and preprocessing the datasets to ensure high data quality. 

#### Feature Selection
Feature selection was critical in reducing model complexity and improving interpretability. Initially, the dataset comprised 61 variables, which underwent rigorous scrutiny to remove redundant features and address issues such as multicollinearity. Using Recursive Feature Elimination (RFE), we identified the top 10 most significant features for fraud detection as shown in the following picture. 

<img width="844" alt="Screenshot 2024-06-28 at 12 29 54 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/fd98bd59-d58f-4fd1-be02-461ad79c229d">

#### Model Development
Three machine learning algorithms were employed for model development: LightGBM, known for its high performance and speed through tree-based learning algorithms; XGBoost, recognized for its efficiency, flexibility, and portability as a distributed gradient boosting library; and Random Forest, which utilizes ensemble learning to construct multiple decision trees for more accurate and stable predictions.

#### Model Evaluation
The performance of the models was evaluated using several metrics, including accuracy, precision, recall, F1 score, and ROC-AUC score. These metrics provided a comprehensive assessment of the models’ effectiveness in identifying fraudulent claims.

### Results
One of the objectives of this study was to develop and evaluate predictive models for detecting fraudulent Medicare claims, with results visualized in the bar chart below. The findings indicate that LightGBM outperformed the other models across all metrics, achieving the highest scores in accuracy (0.807), precision (0.832), recall (0.769), F1 score (0.799), and AUC/ROC score (0.807). These results suggest that LightGBM is particularly effective in distinguishing between fraudulent and non-fraudulent claims. The superior performance of LightGBM can be attributed to its advanced gradient boosting mechanism, which efficiently handles the data’s complexity and variability. The high AUC/ROC score of LightGBM (0.807) demonstrates its robustness in distinguishing between fraudulent and non-fraudulent claims.

XGBoost ranked second, with strong performance metrics, particularly in precision (0.816) and AUC/ROC score (0.790), suggesting it is also a reliable model for fraud detection. Random Forest, while performing adequately, exhibited lower recall (0.734) compared to the other models, indicating it might miss some fraudulent claims. Nonetheless, its overall performance was commendable, making it the third best model among those tested.

<img width="779" alt="Screenshot 2024-06-28 at 12 30 04 PM" src="https://github.com/ariadnear/Capstone_Project/assets/146493977/68fcfbd4-212c-46dc-b85f-d815e06004ee">

Despite the promising results, there are several limitations to consider. The synthetic process used to create the original datasets significantly limits their utility for generating reliable inferences about the actual Medicare beneficiary population. Additionally, while we selected 10 variables for our models, using a greater number of variables could potentially enhance accuracy. While LightGBM and XGBoost were fast and efficient, Random Forest had higher computational costs. Moreover, we were unable to perform a comprehensive grid search due to the computation demand on the large dataset.

For future research and practical applications, several recommendations are suggested. Incorporate additional features and external data sources to improve model accuracy and generalizability. Explore hyperparameter tuning to optimize performance. Validate models in real-world settings to ensure effectiveness and reliability. Establish continuous monitoring and updating mechanisms to detect evolving fraudulent behaviors effectively.

### References
* CMS 2008-2010 data entrepreneurs synthetic puf download page. CMS.gov. (n.d.). https://www.cms.gov/data-research/statistics-trends-and-reports/medicare-claims- synthetic-public-use-files/cms-2008-2010-data-entrepreneurs-synthetic-public-use-file- de-synpuf/de10-sample-1
* Galoustian, G. (2024, January 31). New AI technique significantly boosts Medicare Fraud Detection. Florida Atlantic University. https://www.fau.edu/newsdesk/articles/medicare- fraud-big-data.php
* Gupta, R. A. (2019, May 9). Healthcare Provider Fraud Detection Analysis. Kaggle. https://www.kaggle.com/datasets/rohitrox/healthcare-provider-fraud-detection- analysis/data?select=Test_Beneficiarydata- 1542969243754.csv
* Health care fraud. (2022, October 11). Federal Bureau of Investigation. https://www.fbi.gov/investigate/white-collar-crime/health-care-fraud
* Medicare and Medicaid: Additional actions needed to enhance program integrity and save billions. (n.d.). U.S. GAO. https://www.gao.gov/products/gao-24-107487
* Nabrawi, E., & Alanazi, A. (2023). Fraud detection in healthcare insurance claims using machine learning. Risks, 11(9), 160. https://doi.org/10.3390/risks11090160
* Worstell, C. (2024, January 12). What are the most common types of Medicare fraud? MedicareAdvantage.com. https://www.medicareadvantage.com/enrollment/medicare- fraud

















