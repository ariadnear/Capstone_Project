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




