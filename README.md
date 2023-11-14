UK_Biobank_PingHsien_Yang
2023-11-08
# Introduction

## Cholesterol Impact Analysis on Health Outcome Predictive Models 

This report presents a comprehensive analysis of a dataset that includes a variety of health-related characteristics of a population, with a particular focus on the impact of cholesterol levels on different health outcomes. The analysis involves statistical summaries, correlations, group comparisons by sex and ethnicity, and advanced modeling using a Gradient Boosting Machine (**GBM**).

The dataset includes various histograms, bar charts, and scatter plots that outline the distribution of age, sex, ethnicity, education level, Townsend deprivation index, BMI, cholesterol levels, physical activity, smoking and drinking status, and the occurrence of **dementia**,**myocardial infarction (MI)**, and **stroke**.

## Objectives

The main objectives of the report are:

To elucidate the distribution and influence of **cholesterol** levels on the **population's health outcomes**.
To understand how cholesterol interacts with other variables such as age, sex, BMI, and ethnicity.
To evaluate the predictive power of cholesterol levels for outcomes like MI, dementia, and stroke using GBM.

## model compare
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/00a7b48b-5e21-4f3c-b0c3-10b4e9b257d5)

## Feature compare
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/66190571-8176-4bd0-aa7b-1e7fa6ad8ac1)


# Conclusion

Based on the provided data and model results, we can summarize the effect of cholesterol (Cholesterol) in different disease prediction models as follows:

### Cholesterol Distribution: 
Appears roughly normal with slight right-skewness. No substantial difference in cholesterol levels when comparing gender. Variance is seen across ethnic groups, with Asian and White ethnicities displaying the highest maximum cholesterol levels.

### Effect of Cholesterol on Myocardial Infarction (MI) Modeling:

Cholesterol is one of the most important features in the Myocardial Infarction (MI) prediction model, especially since it accounts for 50% of the feature importance.
From the Partial Dependence Plots, it can be observed that the predictive value Y decreases rapidly as the cholesterol level increases from the lowest value to approximately **4 units**, and then stabilizes as the cholesterol level increases further.
This may indicate that cholesterol levels have a strong negative effect on the risk of myocardial infarction within a certain range, but that the effect diminishes beyond this range.

### Effect of cholesterol on the cognitive disorder (Dementia) model:

In models of cognitive disorders, cholesterol is less important than age and BMI, but still has a place among the important characteristics.
The dependency plots show spikes and troughs at specific cholesterol level points (**3.5 and 8 units**), suggesting that the model is very sensitive to specific points in cholesterol levels, and may imply that cholesterol levels around these points have a specific effect on the predicted variables.

### Effect of cholesterol on stroke (Stroke) modeling:

Cholesterol is also an important feature in stroke prediction models.
The dependency plot shows that when cholesterol levels are within a specific range of low values, the predicted value of Y decreases significantly. However, Y was relatively stable over most of the range of cholesterol levels, suggesting that cholesterol levels have a significant effect on the predictive target only within a specific low range of values(2 to 4).

To sum up, cholesterol levels are notably influential in the prognostic models for cardiovascular conditions such as myocardial infarction and stroke, particularly within the low to moderate spectrum (**2 to 4 units**). It is imperative that clinical attention is heightened when patient cholesterol levels fall within this critical range, as it may significantly alter the predictive outcomes and thereby inform more targeted intervention strategies.
However, in models of brain dysfunction, the effect of **cholesterol** appears to be smaller than that of other characteristics such as age and socioeconomic status. Despite the differences in the predictive contribution of cholesterol to these diseases, maintaining healthy cholesterol levels remains important in the prevention and management of these diseases.

# Recommendations for Further Analysis:
Deeper Statistical Analysis: To clarify the negative correlation between cholesterol and MI outcomes. 
Expanded Data Collection: To better understand cholesterol’s role across different demographics and health profiles.

