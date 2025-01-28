# Impact of Lung Transplant Patient Clinical Characteristics on Post-Operative Blood Transfusion & Patient Outcomes

This repository contains the R code for the data cleaning and analysis for analysis on the impact of blood transfusion (pre-, intra-, and post-surgery) on patient mortality after lung transplantation. 

This analysis aimed to answer the following questions:
- What are the characteristics of patients that require transfusions?
- What are the factors influencing the need and amount of blood transfusions within 24hrs?
- What is the impact of transfusion on 1 year patient mortality?

Our analysis examined a wide range of patient data including patient demographics, surgical information and comorbidities across a time-span of several years.  Our methodology involved: 
- Conducting a literature review to identify which clinical characteristics had a demonstrated impact on postoperative transfusion, along with which elements of transfusion impact patient comorbidities and mortality.
- Using the features determined by the literature search described previously, a binomial Lasso classifier and a Classification and Regression Tree (CART) and Pruned CART models were fit using the presence or absence of a transfusion as the target.
- To create the data for analysis on the effects of variables on patient mortality, a series of kaplan meier curves as well as a Cox Proportional-Hazard model was generated. 

Note on Lasso modeling: A lasso regression model was fit using the predictors identifed in the literature search followed by 5-fold cross validation in the training dataset. This process was repeated 10 times to determine the consistency of model performance, and resilience of predictors to increasing regularization penalties. A final model was fit using the entire data set and the 1SE value as the tuning parameter (determined by 5-fold cross validation).

Key Results:
- Model Selection: Overall, it was found that the Lasso Classifier consistently had the highest performace, and that the average discrimatory power for the lasso classifier was higehr than other models. 
- Relationship with Transfusion Need: Significant predictors of the need for a massive transfusion include the need for life support (intraoperative ECMO), the composition of blood products used, and what type of lung transplane was conducted (right lung transplant is associated with a 44% decrease in transfusion need). All of these
predictors are supported by literature.
- Impacts on Mortality: the Cox Proportional-Hazard model for 1-year mortality found that the only significant variable was BMI with inconsistent findings for other variables. 
  
Repository Structure:
Reading&Cleaning_Data.R: Reading data into R as well as cleaning, pre-processing, and imputation
team_project.R: R file for all data analysis and visualization
transfusion_data.xlsx: raw data file 

Acknowledgments:
We thank the our Professor for BTC1877: Data Science II for providing access to this dataset for this term project

