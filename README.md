# Retail_Consumer_Analytics
Data-driven insights into past &amp; predicted future consumer behavior : Customer Segmentation &amp; Customer Churn Prediction

Data - https://www.kaggle.com/amark720/retail-shop-case-study-dataset?select=prod_cat_info.csv

Project : Retail Shop Case Study Dataset

Why conduct Customer Analytics?
- To create single, accurate view of a customer to make decisions about how best to acquire and retain customers
- Identify high-value customers
- Proactively interact with them
- Better the understanding of a customers buying habits and lifestyle preferences, the more accurate predictive behaviors become and the better the customer journey becomes

Dataset contains following tables
- Customer
- Transactions
- Product

Transaction Table(23K records with no Null value) :
- transaction_id : transaction identifier;
- cust_id : customer identifier;
- tran_date : date of the transaction;
- prod_subcat_code : product sub-category identifier;
- prod_cat_code : product category identifier;
- Qty : product quantity;
- Rate : product price;
- Tax : tax for this purchase;
- total_amt : purchase value + tax;
- Store_type : a type of the store where the purchase was made;


Customer Table(Has %647 unique customers, we’ve got some customers with no information about Gender and city_code):
- customer_Id : customer identifier;
- DOB : customer date of birthday;
- Gender : customer gender;
- city_code : a city where a customer was registered in a store;

Product Table(Has got 23 unique sub-categories, no records with a null value):
- prod_cat_code : product category identifier;
- prod_cat : product category name;
- prod_sub_cat_code : product sub-category identifier;
- prod_subcat : product sub_category name;

Check for following information:
- Date variations
- How many customers the transaction table has?
- How many purchases they made?
- The most popular products

Perform RFM Analysis
- For analyzing customer value
- Commonly used in database marketing, direct marketing
- Received particular attention in retail, professional services industries
- Stands for
    - Recency
    - Frequency
    - Monetary Value
- Other variants :
    - RFD(Recency, Frequency, Duration) :  to analyze customer behavior of viewership/readership/surfing-oriented business products
    - RFE(Recency, Frequency, Engagement) :  border version of RFD, where Engagement can be defined to include visit duration, pages, per visit, or other such metrics
    - RFM-I(Recency, Frequency, Monetary Value - Interaction) : version of RFM modified to account for recency and frequency of marketing interactions with client(e.g. to control for possible deterring effects of very frequent advertising engagements)
    - RFMTC(Recency, Frequency, Monetary value, Time, Churn rate) - augmented RFM model which utilizes Bernoulli sequence in probability theory and creates formulas to calculate the probability of a customer buying at the next promotional or marketing campaign.

Next Steps
- Calculate 3 values : recency, frequency, monetary for every customer in the data set for some period of time, base on half a year for last 3 periods
- RFM score : sum of recency, frequency, monetary value, which allows us to make decisions on a business product or on a customer

Cohort Analysis :
- On 2011 year
- Based on date value
- Defining cohort
- Monthly cohorts based on the month each customer has made their first transaction(received an InvoiceNo due to the InvoiceDate)
- To build an appropriate cohort is to calculate time offsets for each customer transaction

Customer Retention
- How many of all the customers are still ‘alive’(or active)
- % of active customers out of total customers
- Avg quantity of products that customers buy in the store and visualize it in a similar cohort table like that of customer retention analytics

K-Means Clustering based on RFM Scores
- This will help us to clarify and identify users based on their customer behavior metrics

What is K-Means Clustering?
- Popular unsupervised learning methods to identify different patterns
- Simple & fast
- Works well on big datasets

Assumptions with K-Means :
- All variables must have symmetrical distribution and should note be skewed
- All variables should have the same or almost the same average values
- All variables should have the same level of variance

Additional factors to make out cluster more informative & interesting :
- Socio-demographic information about our customers
    - DOB
    - Gender
    - City
- DOB : calculate age of the user on the max date of transaction
- Gender & City : transform with One Hot Encoding
- Next features based on category & transaction information : avg value of purchases by category for every client

Skewness
- It is a measure of symmetry(or lack of symmetry)
- Distribution of dataset is symmetric if it looks the same to the left and right of the center point
- 3 types of skewness :
    - Left Skewed Data
    - Normal Distributed Data
    - Right Skewed Data

Note :  We will be using Z-transformation because we have got negative values that we would like to use in our analysis

Identify number of clusters?
- Visual method : elbow method(the one we will be using)
- The quantitative method : silhouette coefficient
- Experimentation & Imagination

Base metrics to identify the ‘fit’ of the K-Means Algorithm
- Help analyze the relative importance of attributes

Spider Chart
- Helps analyze factors which clusters differ among themselves

Conclusion
- Segmentation allows businesses to make better use of their marketing budgets, gain competitive edge over rival companies, most importantly demonstrate proper knowledge of your customers’ needs and wants
- Other benefits :
    - Marketing Efficiency : breaking down a large customer base into more manageable pieces, making it easier to identify your target audience, launch campaigns to the most relevant people, using relevant channel
    - Determine new marketing opportunities : during the process of grouping customers into clusters, you may find that you’ve identified a new market segment, which could int urn alter your marketing focus and strategy to fit
    - Better brand strategy : once you’ve identified the key motivators for your customers, such as design or price, or practical needs, you can brand your products appropriately
    - Improve distribution strategies : identify where customers shop, when can informatively shape product distribution strategies like what type of products are sold at particular outlets
    - Customer Retention : Using segmentation, marketers can identify groups that require extra attention and those that churn quickly, along with customer with the highest potential value. It can also help with creating targeted strategies that capture your customers’ attention and create positive high-value experiences with your brands.
