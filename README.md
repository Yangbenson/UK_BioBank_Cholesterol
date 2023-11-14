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

### summary variables after data cleaning
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/328828d6-94c0-4b80-a121-66b82f50eefc)

**age:** This is a histogram showing the distribution of ages. It looks
like a more normal distribution, but may be right-skewed (most
individuals are clustered on the lower age side).

**sex:** This is a bar chart showing the distribution of sex in the
dataset. There are two categories: female (F) and male (M). As you can
see, the number of females in the sample is larger than the number of
males.

**ethnicity_group:** This bar chart shows the distribution of different
ethnic groups. Ethnicity 1 (white) is in the majority.

**education_college_university:** This histogram appears to show the
distribution of college-educated people with a larger number of
non-college professors.

**townsend_deprivation_index:** This is a histogram showing the
distribution of the Townsend Deprivation Index. This index may be a
measure of the socio-economic status of the area. It is left-skewed
(most individuals are concentrated on the lower side of the index).

**bmi_0:** This histogram shows the distribution of body mass index
(BMI). The data appears to be more normally distributed and concentrated
within a certain interval.

**cholesterol_0:** This is a plot of the distribution of blood
cholesterol levels. The data appears to be close to normally
distributed, perhaps slightly skewed to the right.

**MET_activity:** This histogram represents a measure of exercise. The
distribution shows a lot of small peaks, which may represent a breakdown
of different activity levels.

**smoking_status_0:** This bar graph shows the distribution of smoking
status, coded with numbers to indicate different smoking statuses.

**alcohol_status_0:** This is another bar chart showing the distribution
of drinking status, again coded with numbers.

**dementia_all_outcome:** This bar chart shows the distribution of
dementia outcomes, with 0 and 1 indicating the absence and presence of
dementia.

**MI_all_outcome:** This bar graph shows the distribution of all
myocardial infarction outcomes, with 0 and 1 indicating the absence and
presence of myocardial infarction.

**stroke_all_outcome:** This bar chart shows the distribution of all
stroke outcomes.

### Correlation Heatmap

![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/878e0dce-02ee-4d15-a491-a2dfd460b7e9)

The heatmap shows that most variables have a very low correlation with
each other since the majority of the values are close to 0. However,
there are some notable correlations, such as:

1.A moderate **positive** correlation (0.13) between
**dementia_all_outcome** and **stroke_all_outcome**, suggesting that
individuals who have had a stroke might be more likely to be diagnosed
with dementia.

2.A small **positive** correlation (0.11, 0.12) between **age**,
**dementia_all_outcome**, **MI_all_outcome** and **stroke_all_outcome**,
implying that the likelihood of having a heart attack or stroke may
increase with age.

3.A small **negative** correlation (-0.1) between **cholesterol** and
**MI_all_outcome**,This means that with a slight decrease in cholesterol
levels, there was a slight increase in the incidence of all outcomes of
heart attacks.

4.A small **positive** correlation (0.09) between **BMI** and
**MI_all_outcome**, implying that the likelihood of having a heart attack
with higher BMI.

5.A small **positive** correlation (0.08) between
**townsend_deprivation_index** and both **BMI** and **Smoke_status**,
suggesting that as deprivation increases, there tends to be a slight
increase in BMI and a higher likelihood of smoking. But a
small**negative** correlation (-0.08) with **alcohol_status**, where higher
deprivation scores are associated with a slight decrease in
alcohol_status.

However, those associations are fragile, suggesting that there is no
solid direct relationship between each variables. Those slight
correlations between each are not sufficient to indicate a clear trend or
to inform clinical decisions. More comprehensive studies are needed to investigate the relationship between these variables further.

### model compare
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/00a7b48b-5e21-4f3c-b0c3-10b4e9b257d5)

This graph shows the distribution of RMSE (Root Mean Square Error) for
three different statistical models. In forecasting models, RMSE is a
standard measure of the difference between the model's predicted value and
the actual observed value. Generally speaking, the lower the RMSE, the
higher the accuracy of the model.

The three models are:

1.**Logistic regression**  2.**Support Vector Models**   3.**Gradient Boosting**

As can be seen from the violin plot, **Gradient Boosting** has lowest
RMSE, which means it has better predictive accuracy. Therefore, for
further analysis and model interpretation, I will choose the **radient
Boosting model**, taking into account the stability and high accuracy of
its prediction results.

### Cholesterol analysis model with tuning Gradient Boosting
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/5888f19e-d5b7-43a7-9f75-08fb6f629e74)


### Disease report
### MI
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/3c773389-81ce-4d7f-8d8f-15b8ab91a361)

### Dementia
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/cc02c563-ec8d-4ac1-887b-9d79ae559e14)

### Stroke
![image](https://github.com/Yangbenson/UK_BioBank_Cholesterol/assets/118023370/66190571-8176-4bd0-aa7b-1e7fa6ad8ac1)


We use the binomial distribution ("bernoulli") method for modeling.

We used **Youden's J statistic** to choose the threshold for prediction. This
is a statistical method used to select a threshold that maximizes the
difference between the actual and false favorable rates to find a good
balance.

Feature Importance Bar Chart: 
This graph shows which variables have the most influence
in the model predictions.

partial dependence plots: They are used to demonstrate the relationship between one or two features and model predictions, regardless of the influence of other features.

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

