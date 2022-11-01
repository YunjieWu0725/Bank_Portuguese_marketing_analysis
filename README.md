# Bank_Portuguese_marketing_analysis
The dataset is from https://data.world/login?next=%2Fdata-society%2Fbank-marketing-data%2Fworkspace%2Ffile%3Ffilename%3Dbank-additional-names.txt

Some extra data cleaning has been done by using Excel, which include data cleaning, outlier treatment, data categorization, and data creation.   
1 Missing Data:
There is no missing value in this dataset. However, there are values like “unknown”, and “others”, which are useless. They can be treated as a missing value. 

●In the column “job”, there are 330 records showing “unknown”, so we delete them from our dataset.

●In the column “default”, there are 8445 records showing “unknown”, which is a big number. And there are only 3 records showing “yes”, so we decide that we will not use this column.

●In the column “housing”, there are 985 records showing “unknown”, so we removed them.
![image](https://user-images.githubusercontent.com/106036393/199175109-2fe08308-6390-4c12-9e8b-3d6e85eb42ec.png)

2 Outlier Treatment:

In the below box plots of columns “duration” and “campaign” (figure1.1), there are some “outliers” values. One method to treat outliers is removing them from the dataset so we applied it to our dataset to get a better analysis. The following formula was used to identify the outliers (Q3 + 1.5×IQR). This shows that values of duration beyond 647 and values of campaigns larger than 6 are outliers, so we deleted them. This led to the removal of 2856 records.

3 Data Categorization:

As illustrated in the chart (figure 1.2), the participants are in the range of 30 to 59 years old. we have discretized the ages column into 4 groups. Considering those who are younger than 29 years are in the fundamental level of the companies, those who are between 30-45 years are in the middle level, who are between 45-59 years are in the high level, and who are 60 years or older are retired and use their own pensions.
![image](https://user-images.githubusercontent.com/106036393/199175126-3c35b643-a4e8-40d7-8e2c-fdaf3f08e72b.png)

4 Data Creation:

To show whether pdays influence customer decisions, a new variable has been created called “is_contact_before”, which has values 0 for those who haven’t been contacted before and 1 for those who have been contacted. It is shown that clients who have been contacted before are more willing to accept the loan. Further, the actual number of days may not be so affectable.

5 Feature Selection:
The dataset has 28545 of 31156 records whose “poutcome” equals “nonexistence”. We keep this column because if the customers don’t receive the contact before, the majority of them will not accept the loan. However, if the customer accepted the loan in the past campaign, he will be more likely to accept the loan at this time.
