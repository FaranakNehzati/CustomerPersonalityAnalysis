# CustomerPersonalityAnalysis
![people](https://user-images.githubusercontent.com/59418722/145105266-8292c387-ade8-4921-aae4-d73b99b8074b.jpg)

## Introduction
Customer Personality Analysis is a detailed analysis of a company's different types of customers. It helps businesses to understand their customers and come up with the best sales and campaigns to serve them better. 
One example can be instead of spending money to market a new product to every customer in the database; it can analyze which segment is most likely to buy that product then market to them.
I will perform a clustering analysis on the customer’s Dataset. This is a public dataset from Kaggle website. there is no name and there is only customer ID number. there is no ethical issues with using this dataset.
## Description
Dataset has 29 columns. The first Columns are about people and their income, education, and children, etc. Then the amounts of different types of product they bought. I will make one column from all and name it “totalMNT.”
And the 3rd part of the dataset is about the different types of purchases. I will make a total column for that as well. 
I uploaded the data in BigQuery for precleaning. I used the query below to make a new table and import it to a Jupyter notebook. 
``` Sql 
SELECT
  ID,
  Education,
  Marital_Status,
  Income,
  Kidhome,
  Teenhome,
  Dt_Customer,
  Recency,
  MntWines,
  MntFruits,
  MntMeatProducts,
  MntFishProducts,
  MntGoldProds,
  NumDealsPurchases,
  NumWebPurchases,
  NumCatalogPurchases,
  NumStorePurchases,
  NumWebVisitsMonth,
  AcceptedCmp1,
  AcceptedCmp2,
  AcceptedCmp3,
  AcceptedCmp4,
  AcceptedCmp5,
  Complain,
  Response,
  2014 - Year_Birth AS Age,
  Kidhome + Teenhome AS Children,
  MntWines + MntFruits + MntMeatProducts + MntFishProducts + MntSweetProducts + MntGoldProds AS totalMnt
FROM
  `capstoneproject-334219.customerData.customerData`
  ```
To see the methodology and steps taken in Python go to Jupyter Notebook.
[this link](https://github.com/FaranakNehzati/CustomerPersonalityAnalysis/blob/main/FN_capstone.ipynb)

## Further EDA in Tableau

After clustering in python I made a CSV file from dataset with new column called "clusters". And uploaded it to Tableau for some more exploratory data analysis.
I identify clusters with the relative number that model gave them. To view the Dashboard go to [this link](https://public.tableau.com/views/FN_customerAnalysis/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link)

I enclude a picture of the Dashboard here:

<img width="550" alt="FN_Dashboard" src="https://user-images.githubusercontent.com/59418722/145108352-9022778a-5278-4984-9aad-feba60bd58b3.png">

## Results and insights
I identify clusters with the relative number that model gave them. Each one has the following characteristics:

Cluster 0. Lowest income overall. Second high buyer. They have the most kids. We need to focus on low cost campaigns and sales to target them.

Cluster 1. Low income and low spenders. Usually single. We need to find out why they don't purchase more.

Cluster 2. The Elite cluster. They are second high earners and highest spenders. These ones need to be targeted for all high end campaigns. They are usually in a relationship and have the second most kids.

Cluster 3. The richest cluster. But second low spenders. They have the best response to campaigns and don't have many kids. We need to focus on this cluster to find out why these high earners don't spend so much money. Maybe a different type of campaign or more options can make these people buy more.







