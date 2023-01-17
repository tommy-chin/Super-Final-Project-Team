# Exploring Death in the ICU
 
Our main goal is to anaylyze the importance of certain vitals from patients staying in the ICU in the effort to predict survivability. 

## Why?

In addition to our curiousity regarding our own mortality, we thought this would be a good opportunity to learn about the aspects of our health that could be the difference between life and death! This dataset is very rich, over 150 columns of information per patient! One of our primary goals is to use supervised machine learning to determine what 5-10 features have the most impact on a patients survival. 

The ICU is a unique department of any hospital. Many patients are not in a state to communicate their medical history. We would like to high-light the importance of taking vitals, and the valued information about the patient can be surmised from standard hospital tests and measurements. 



It would be truly fascinating if we could compare our data with healthcares guidelines to see if we came to a similar conclusion. We will be communicating via slack to evenly divide all imporant tasks and to notify the team of any new discoveries. 
## Technologies, languages, tools, and algorithms used
Python and Pandas were used to perform all of the data preprocessing. We decided to use sklearn which gave us access to Random Forest Classifer, Logisitic Regression, train_test_split, and StandardScaler. Random Forest Classifier was our supervised machine learning model that we settled on. StandardScaler allowed us to properly scale our dataset so it was able to be properly put through a training and testing split. Logisitic regression then allowed us view the accuracy scores of our training and testing sets. For our database, we decided to use Amazon's RDS which would host our PostGresSql server that we worked with on PgAdmin4. Our dataset was stored on a S3 bucket through AWS. 

## Machine Learning Model
### Description of preliminary data preprocessing 
Before we were able to perform any sort of machine learning on our dataset, the dataset needed to be cleaned. There were a total of 186 columns in the original dataset and many of these columns contained a great number of NaN values. Our inital approach was to simply drop all of the rows with any NaN values but after doing so, we realized that many of the columns in the dataset had NaN values which led to an overwhelming number of rows being dropped. Instead, the dataset was checked to see which columns had the least amount of NaN values. From this, a general idea of which columns would be included in the cleaned dataframe was established. 
### Description of preliminary feature engineering and preliminary feature selection, including their decision-making process
From these columns, 20 columns were chosen since we deemed them likely to be useful in our machine learning process. A new dataframe was created with these 20 columns and any existing rows with NaN values were dropped. To see whether or not the columns we chose were important or not, we also created a PCA to better understand which columns had the most significant features. The PCA confirmed that the columns we selected were infact significant. 
### Description of how data was split into training and testing sets 
We were interested in seeing how different factors influenced whether or not a patient would have a hospital death or not when admitted into the ICU. Since this was our interest, our training and testing sets were split between the outcome of hospital death and all of the other factors that could have an influence on hospital death. Since there was a great range of values in each column, we needed to scale the data in order to proceed with our machine learning model. 
### Explanation of model choice, including limitations and benefits
Since our dataset had labeled data, it was natural for us to perform a supervised machine learning model. The model that we chose was random forest classifer so that we could better understand the importance levels of each individual column. The random forest classifer has many benefits and one of them being that it is an ensemble learning technique which helps reduce overfitting and variance. This helps us our machine learning model have a better accuracy score. Since our cleaned dataset has 77,974 rows, it is quite possible that there are outliers in the dataset that could skew our results. However, random forest classifier is shown to be robust to outliers. A limitation of random forest classifer is that since our cleaned dataset is large, there are many decision trees to be made which leads to the model having a long training time which also requires more computational power.
### Explanation of changes in model choice
Random forest classifier was chosen for our supervised machine learning model from the start. However, the dataset that we used for this model had gone through various changes. Originally, we had run random forest classifier on a dataset with all rows that had NaN values dropped. Although this gave us an understanding on what columns may have been important, the low number of rows left in the dataset and the low accuracy of the testing score prompted us to revisit our data preprocessing. Once we established our current cleaned dataset, we decided to run random forest classifer on 10% of the dataset to have a better understanding of how the training and testing scores would look on the whole dataset. The reasoning behind this was to save computing time on the off chance that the training and testing scores were not acceptable. After running random forest classifer on the whole cleaned dataset, it was shown to have similar training and testing scores to the model ran on 10% of the dataset.
### Description of current accuracy score
After fitting our Random Forest Classifier, our cleaned dataset had a training score accuracy of 0.919 and a testing score accuracy of 0.921. 
## Link to Google Slides
https://docs.google.com/presentation/d/1hRXXjuN23n1NzC3Kvboo2ra6cVmhRnCKV_u7cMkz-D0/edit?usp=sharing



