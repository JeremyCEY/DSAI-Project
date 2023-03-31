# SC1015 Data Science Project - _Uncover the secrets of sleep_

Our team's objective is to identify how a person’s sleep is affected by a persons's lifestyle choices, and to predict person's quality 













# Introduction

## Objective

> Detailed Introduction to your project, e.g. what problem you are going to solve based on what dataset
Through our dataset on sleep efficiency, we hope to be able to identify which factors are important in determining a person’s sleep quality, and how influential those factors are. We aim to understand how sleep is affected by a person's lifestyle choices and hope to find out how to improve sleep quality.

Problem Formulation:
To predict sleep quality based on lifestyle choices.

## Significance

To obtain quality sleep is a problem that is faced by many people around the world. Sleep duration is important, as it can indicate that several complete sleep cycles have taken place, a study has suggested that sleep quality is what ultimately restores the brain. According to the National Institutes of Health, 7% to 19% of adults reportedly do not get enough sleep, and 40% reportedly fall asleep during the day at least once a month. Moreover, university courses in Singapore are known for their rigor and heavy workload. This may potentially impact students' sleep activity negatively. 

## Organisation
### - Data Preprocessing
    - Importing Libraries
    - Importing Data Set
    - About Data Set

### - Relationship between gender and age to sleep efficiency
### - Sleep Percentages
    - Sleep cycle and its stages (Light Sleep VS Deep Sleep VS REM Sleep)
    - Relationships between Sleep Duration and Sleep Percentages
    - Relationships between Sleep Efficiency and Sleep Percentages
### - Sleep Quality
    - What determines Sleep Quality?
    - Relationship of lifestyle choices (bed time, sleep duration, exercise, caffeine, alcohol, smoking) to sleep quality (5 factors)

### - Principal Component Analysis (PCA)
    - Coming up with the weightage of each factors in Sleep Quality

### - Creating and testing Machine Learning Models
    - Choosing Relevant factors
    - Train a model to determine an average recommended sleep duration
#### 1. Univariate Linear Regression Model
#### 2. Multivariate Regression Model
#### 3. Random Forest Regression Model
## About Data Set
#### The dataset contains information about a group of test subjects and their sleep patterns. 
Dataset: https://www.kaggle.com/datasets/equilibriumm/sleep-efficiency
Each test subject is identified by a unique "Subject ID" and their age and gender are also recorded. The "Bedtime" and "Wakeup time" features indicate when each subject goes to bed and wakes up each day, and the "Sleep duration" feature records the total amount of time each subject slept in hours. The "Sleep efficiency" feature is a measure of the proportion of time spent in bed that is actually spent asleep. The "REM sleep percentage", "Deep sleep percentage", and "Light sleep percentage" features indicate the amount of time each subject spent in each stage of sleep. The "Awakenings" feature records the number of times each subject wakes up during the night. Additionally, the dataset includes information about each subject's caffeine and alcohol consumption in the 24 hours prior to bedtime, their smoking status, and their exercise frequency. For more information, read 'data_description.txt'.
### Splitting the Variable Types

#### Numerical Variables:
- age
- sleep_efficiency


#### Categorical Variables:
- gender
- bedtime
- wakeup_time
- sleep_duration
- rem_sleep_percentage
- light_sleep_percentage
- deep_sleep_percentage
- smoking_status
- awakenings
- exercise_frequency
- alcohol_consumption
- caffeine_consumption

## Sleep Percentages

### Light Sleep vs Deep Sleep vs REM Sleep
According to sleepfoundation.org, 1 sleep cycle occurs in 4 stages, 2 stages of light sleep followed by 1 stage of deep sleep and 1 stage of REM sleep.

Stages 1-3 are types of non-rapid eye movement (NREM) sleep, while 

Stage 4 is a type of rapid eye movement (REM) sleep.

#### Light Sleep
Stage 1 (Light Sleep): As your brain slows down, low-amplitude mixed-frequency (LAMF) activity replaces the alpha brain waves that took over as you became drowsy. Your body has some muscle tone, and your breathing is regular.

Stage 2 (Light Sleep): Your heart rate and body temperature both decrease. Sleep spindles and K-complexes, specific brain wave patterns, begin occurring as you continue transitioning toward deep sleep.

#### Deep Sleep
Stage 3 (Deep Sleep): Also called slow-wave sleep, occurs in the third stage of NREM sleep. Typically, you descend into deep sleep within an hour of falling asleep, and experience progressively shorter periods of deep sleep as the night wears on. During deep sleep, body functions like breathing and heart rate are also very slow and your muscles are relaxed. It can be difficult for someone to wake you up, and waking up out of deep sleep may make you feel mentally foggy for up to an hour. It is the most sleep stage out of the 4.

#### REM Sleep
Stage 4 (REM Sleep): It is a stage of sleep associated with dreaming and memory consolidation. You experience your first cycle of REM sleep about 60 to 90 minutes after falling asleep. As part of a full night’s sleep, you cycle through four stages of sleep multiple times: three stages of non-REM sleep, followed by one stage of REM sleep. Each cycle through all the sleep stages takes 90 to 120 minutes to complete. With each new cycle, you spend increasing amounts of time in REM sleep, with most of your REM sleep taking place in the second half of the night.
## Principal Component Analysis (PCA)
In this portion, we will use PCA which is a technique for reducing the dimensionality of a dataset by identifying the most important underlying patterns or features. We apply PCA to the existing variables (sleep efficiency, deep sleep percentage, REM sleep percentage, number of awakenings) to identify the principal components that explain the most variance in the data. Based on the the contribution of each variable to the principal components, we can assign weights to each of the existing variables.
1. Data Preparation: 
Collect data on the different factors that contribute to sleep quality, such as sleep efficiency, deep sleep percentage, REM sleep percentage, and number of awakenings. The data should be in a numerical format and should be normalized so that each variable has a mean of 0 and a standard deviation of 1.

2. Perform PCA: 
Apply PCA to the normalized data to identify the principal components that explain the most variance in the data. The number of principal components to keep should be determined by examining the explained variance ratio or scree plot, and selecting the number of components that capture a sufficient amount of variance in the data.

3. Interpret Principal Components: 
Examine the loadings of each variable on the principal components to understand which variables contribute the most to each component. The loadings represent the correlation between each variable and the principal component, and can be positive or negative. Variables with high absolute loadings are most strongly associated with the principal component.

4. Calculate Weights: 
Once the principal components and variable loadings are identified, the weights for each variable can be calculated based on their contribution to the principal components. For example, the weight for sleep efficiency could be based on its loading on the first principal component, while the weight for deep sleep percentage could be based on its loading on the second principal component.

5. Calculate Sleep Quality Score: 
Finally, the sleep quality score can be calculated as a weighted sum of the different variables using the weights identified in step 4. For example, the sleep quality score could be calculated as:

Sleep Quality Score = w1 * Sleep Efficiency + w2 * Deep Sleep Percentage + w3 * REM Sleep Percentage - w4 * Number of Awakenings

where w1, w2, w3, and w4 are the weights calculated based on the PCA analysis.

It's important to note that PCA is just one approach to identifying weights for the different variables. The weights identified using PCA may not be optimal for all datasets or contexts, so it's important to carefully evaluate the results and consider other approaches as well.


## data processing
## eda
## multivariate regression
## random forest regression
## sleep efficiency


sleep-efficiency.csv
-raw data
clean-sleep-efficiency.csv
-saved after preprocessing
-can use raw or this one for eda
pca-sleep-efficiency
-saved after pca
-use for all models