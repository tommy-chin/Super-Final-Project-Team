# Exploring Death in the ICU
 
When healthcare workers measure and analyze the vitals included in our dataset, they are provided an insight into the medical history of the patient. This is particularly important in the ICU wing, since patients are often not in a consious state. Of course medical history can be requested from another hospital, however it could take hours or days to recieve. Frankly, patients in the ICU do not have the time to wait. 


In this study, we will identify the factors that have the most impact predicting survivability using a supervised machine learning model. We are building this model on an extremely diverse dataset, with information from 366 hospitals in the United States, Australia, and New Zealand. We will then attempt to visualize their influence in an effort to educate those new to the healthcare profession. We hope that this motivates hospital staff to diligently study vitals and reassure them of their role's importance.

We will be communicating via slack to evenly divide all imporant tasks and to notify the team of any new discoveries. 

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



