# Exploring Death in the ICU
 
Our main goal is to anaylyze the importance of certain vitals from patients staying in the ICU in the effort to predict survivability. 

## Why?

In addition to our curiousity regarding our own mortality, we thought this would be a good opportunity to learn about the aspects of our health that could be the difference between life and death! This dataset is very rich, over 150 columns of information per patient! One of our primary goals is to use supervised machine learning to determine what 5-10 features have the most impact on a patients survival. 

The ICU is a unique department of any hospital. Many patients are not in a state to communicate their medical history. We would like to high-light the importance of taking vitals, and the valued information about the patient can be surmised from standard hospital tests and measurements. 



It would be truly fascinating if we could compare our data with healthcares guidelines to see if we came to a similar conclusion. We will be communicating via slack to evenly divide all imporant tasks and to notify the team of any new discoveries. 

## Machine Learning Model
### Description of preliminary data preprocessing 
Before we were able to perform any sort of machine learning on our dataset, the dataset needed to be cleaned. There were a total of 186 columns in the original dataset and many of these columns contained a great number of NaN values. The dataset was first checked to see which columns had the least amount of NaN values. From these columns, 19 columns were chosen since we deemed them likely to be useful in our machine learning process. A new dataframe was created with these 19 columns and any existing rows with NaN values were dropped. 
### Description of preliminary feature engineering and preliminary feature selection, including their decision-making process
### Description of how data was split into training and testing sets 
We were interested in seeing how different factors influenced whether or not a patient would have a hospital death or not when admitted into the ICU. Since this was our interest, our training and testing sets were split between the outcome of hospital death and all of the other factors that could have an influence on hospital death. Since there was a great range of values in each column, we needed to scale the data in order to proceed with our machine learning model. 
### Explanation of model choice, including limitations and benefits
Since our dataset had labeled data, it was natural for us to perform a supervised machine learning model. The model that we chose was random forest classifer so that we could better understand the importance levels of each individual column. The random forest classifer has many benefits and one of them being that it is an ensemble learning technique which helps reduce overfitting and variance. This helps us our machine learning model have a better accuracy score. Since our cleaned dataset has 77,974 rows, it is quite possible that there are outliers in the dataset that could skew our results. However, random forest classifer is shown to be robust to outliers. A limitation of random forest classifer is that since our cleaned dataset is large, there are many decision trees to be made which leads to the model having a long training time which also requires more computational power.

## Link to Google Slides
https://docs.google.com/presentation/d/1hRXXjuN23n1NzC3Kvboo2ra6cVmhRnCKV_u7cMkz-D0/edit?usp=sharing



