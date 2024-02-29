# EDA-Churn-Analysis
# Business Understanding 
In the telecommunications industry, customer churn refers to the rate at which customers discontinue their service with a company over a given period of time. Understanding and reducing customer churn is crucial for telecom companies as it directly impacts revenue and profitability. By analyzing factors contributing to churn and implementing targeted strategies, telecom companies can improve customer retention and enhance overall business performance.

# Overview
This analysis focuses on understanding customer churn in the telecom industry. I explore a dataset containing various attributes of telecom customers, including demographic information, usage patterns, and service subscriptions. By leveraging data analytics techniques, I aim to uncover insights into customer behavior and identify factors that influence churn. The findings from this analysis will inform strategic decision-making and help devise effective retention strategies to mitigate churn and foster long-term customer relationships.

# Understanding the Data
Total Colums 21
Numerical - 3
Float - 1
Integer - 2
Object -18
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/cfdcd0f0-9d55-4ab2-9823-546ff98cc6d2)

# Target Variable - "Churn"
Overall Churn rate is 26.58%.
This indicates that approximately 26.5% of customers discontinued their service with the telecom company over the analyzed period. 
Understanding and addressing factors contributing to this churn rate are crucial for the company's efforts to improve customer retention and reduce revenue loss.
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/254ff4d2-3aaa-4a0b-9995-03a195075287)

# Data Preperation & cleansing
Variable "TotlaCharges" is Object type but vlaues are continuous. So, converting it into Float type.

## Identifying and Handling Missing values
Only one column has missing data: “TotalCharges”
When the “TotalCharges” column is converted from Object type to float, we identified missing values in it.
As % of the missing value is very low i.e. 0.15%, it is safe to remove those values. We can also impute the missing vlaues using Mean() or median().
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/5fb8a6e8-9028-4b39-93c0-c86c10d2a21d)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/66a8cb3d-5f6b-4569-a7f9-a57795b63240)

## Converting Numerical to Categorical
Variable "tenure" is having integer value from Min: 1 to Max: 72 and it is difficult to visualize this through graph. Therefore, created the new categorical variable "tenure_group" and putting these values in bins of 1-12, 12-24,....,60-72.
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/48f56101-8b6a-49af-9e1b-2d293e8f2fc8)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/710e74e1-bca7-4bb6-8957-ad49bf0b9947)

## Dropping Unnecessary columns
Since we created new variable "tenure_group", now "tenure" is not needed. Also, varibale CustomerID doesn't have any importance in this analysis. Therefore, dropping the CustomerID and tenure.

#  Analysis
## Univariate Analysis
### Categorical Analysis
We have done anlaysis of each variable with "Churn" varible.
#### Gender vs Churn
With a 26.95% churning rate, females churn slightly more than Males(26.20%).
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/01e1f391-11a4-4933-b1a8-a54974a4f8a0)
#### Senior Citizen vs Churn
Senior citizens are more likely to churn with a churn rate of 41.68%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/e4e2cde0-3933-435e-a9ed-46913a81797d)
#### Partner vs Churn
Individuals without partners exhibit a higher churn rate compared to those with partners. 
Churn rate:
Without Partner – 32.97%
With Partner – 19.71%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/31b49f77-1f51-4353-98a1-a0144538d1e4)
#### Dependent vs Churn
Independent Individuals are more likely to churn compared to dependents. 
Churn rate:
Dependent – 15.53%
Independent – 31.27%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/5a42f41b-5166-4e24-bb69-7aca1e5fd0b2)
#### PhoneService vs Churn
customers with phone service have a slightly higher churn rate of 26.74% compared to those without. However, it's important to note that the proportion of customers without phone service is significantly lower. 	
Churn rate:
Without Phone services – 25%
With Partner – 26.74%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/bd52a933-999c-43aa-bee7-bcf28882cec4)
#### Multiplelines vs Churn
There is a notable difference in churn rates between customers with and without multiple lines, with rates of 28.64% and 33.47% respectively. This suggests that the presence of multiple lines may contribute to a lower churn rate, potentially indicating greater satisfaction or engagement among this customer segment

Churn rate:
With Multiple Lines – 28.64%
Without Multiple Lines – 33.47%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/7a016d76-5493-4593-a713-a15ab9db85e8)
#### InternetService vs Churn
The churn rates vary significantly across different internet service types, with Fiber optic customers experiencing the highest churn rate at 41.89%, followed by DSL at 18.99%, and the lowest churn rate observed among customers with No Internet Service at 7.43%.	
Churn rate:
DSL– 18.99%
Fiber optic – 41.89%
No Internet Service – 7.43%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/ee8f41bc-1bd6-4c35-8af8-db81f7a0a9c8)
#### OnlineSecurity vs Churn
The presence of online security appears to correlate with a lower churn rate of 14.64%, contrasting sharply with the higher churn rate of 41.77% among customers lacking such protection.
Churn rate:
Online security – 14.64%
No online security – 41.77%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/78e82491-a912-4936-a0a4-8fb885b37764)
#### DeviceProtection vs Churn
Customers with device protection exhibit a relatively lower churn rate of 22.53%, in contrast to those without device protection, who demonstrate a higher churn rate of 39.14%.	
Churn rate:
Device Protection – 22.53%
No Device protection – 39.14%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/d301717c-d892-4296-b1e1-ffa3c17da8af)
#### TechSuport vs Churn
Customers with access to tech support show a notably lower churn rate of 15.19%, while those without such support exhibit a higher churn rate of 41.64%.
Churn rate:
Tech Support – 15.19%
No Tech support – 41.64%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/d89e2243-a18f-4ae3-9a3e-8c452ac49758)
#### StreamingTV vs Churn
Customers with streaming TV services demonstrate a churn rate of 30.11%, while those without streaming TV services have a slightly higher churn rate of 33.53%.	
Churn rate:
With Streaming TV– 30.11%
Without Streaming TV– 33.53%
No Internet Service – 7.43%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/0558866c-b2c4-4e35-a260-fc967ac97764)
#### StreamingMovies vs Churn
Customers with streaming movie services exhibit a churn rate of 29.95%, whereas those without streaming movie services show a slightly higher churn rate of 33.72%.
Churn rate:
With Streaming Movies – 29.95%
Without Streaming Movies – 33.72%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/2da0c91c-d014-4ad4-be6b-c4edc13b8e72)
#### PaperlessBilling vs Churn
Customers enrolled in paperless billing display a higher churn rate of 33.58%, whereas those not enrolled have a notably lower churn rate of 16.37%.	
Churn rate:
With Paperless Billing – 33.58%
Without – 16.37%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/665e671a-e579-4988-b5dc-3ca0f5229409)
#### PaymentMethod vs Churn
Customers using electronic check for payments exhibit a substantially higher churn rate of 45.28% compared to other payment methods.
Churn rate:
Electronic check – 45.28%
Mailed check – 19.20%
Transfer - 16.73%
Card - 15.25%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/a2f8da0a-af14-47b8-852e-e8cb7261c736)
#### Contract vs Churn
Customers with month-to-month contracts exhibit the highest churn rate at 42.70%, whereas those with one-year contracts show a significantly lower churn rate of 11.27%. Interestingly, customers with two-year contracts demonstrate the lowest churn rate at 2.84%.
Churn rate:
Month to Month Contract – 42.70%
One-year Contract – 11.27%
Two Year – 2.84%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/cc5bfea3-5f76-441e-b94c-b9a95b0914b4)
#### TenureGroup vs Churn
It is revealed that customers with less tenure are likely to churn more while those with long tenure churn less.
Churn rate:
Tenure group
1-12 – 47.67%
61-72 – 6.6%
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/fedb037f-b922-441f-8361-1a5faa2dca88)

### Numerical Analysis
#### Monthly Charges vs Churn
There exists a direct proportionality between monthly charges and churn, indicating that as the monthly charges increase, the churn rate also increases. This suggests that higher monthly charges may contribute to a higher likelihood of churn among customers.
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/055d1a03-e5dc-470b-95a6-bf2afb6c025c)
#### Total Charges vs Churn
When total charges are lower, there is a corresponding increase in churn rate. This suggests an inverse relationship between total charges and churn, indicating that customers with lower total charges are more likely to churn.
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/b6e279c6-12fc-4195-858a-b62952f99644)

### Finding Correlation
To find correlation, converting Categorical variables into Numerical withthe use of feature encoding (Dummy Encoding).
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/af26e903-b279-4ebc-9fab-04c48e454336)
Variables such as Contract_Month-to-month, OnlineSecurity_No, TechSupport_No, tenure_group_1-12 have a positive high correlation to Churn variable.

### Bivariate Analysis
#### Distribution of Gender and Partner for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/79a30dbb-9b22-4816-b7f1-67693ff5bfa4)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/42b42ba1-0fd9-47fd-89a4-48a4b7cf801a)
Churn rate
Males with Partner -  20.46%
Females with Partner - 18.95%
Males without Partner - 31.53%
Females without Partner -  34.44%
Insight
Both Males and Females without partners are more likely to churn. Females with no partner have the highest churn rate.

#### Distribution of Gender and SeniorCitizen for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/858ad929-dabf-4766-8311-8cda7580a7d3)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/4d549c77-f210-4fba-bcea-57cc848f7ebe)
Churn rate
Senior citizen Males -  41.11%
Senior citizen Females – 42.25%
Insight
The churn rate among senior citizen males is 41.11%, while senior citizen females exhibit a slightly higher churn rate of 42.25%. This suggests a comparable churn behavior between senior citizen males and females.

#### Distribution of Gender and Dependents for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/2af9c21b-cb1b-4731-b3a2-c069e03bc463)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/913e0dcd-4107-4c05-8f3a-eab4cb65f27a)
Churn rate
Independent Males -  31.09%
Independent Females –  31.46%
Insight
This indicates a similar churn behavior between males and females who are not dependent.

#### Distribution of Gender and Tenure for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/cfd024b5-5133-4cc7-a9e4-bf4385690c24)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/54f5645b-74b3-4dd9-b81e-e996993e44c3)
Churn rate
Males with tenure group 1-12 -  46.16%
Females with tenure group 1-12 - 49.21%
Insight
Almost 50% of females with having tenure of 1-12 months are likely to churn, while 46% of males churn when having a short tenure of 1-12 months.

#### Distribution of Gender and Contracts for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/ee240ea5-0aa2-48a6-b565-ec04220477a5)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/f38ef6ef-ddd1-461a-bee2-bc4b421884ee)
Churn rate
Males with a month-to-month contract -  41.69%
Females with a month-to-month contract – 42.54%
Insight
The churn rate among males with a month-to-month contract is 41.69%, while females with the same contract type exhibit a slightly higher churn rate of 42.54%. This indicates a similar churn behavior across gender lines for customers with month-to-month contracts

#### Distribution of Gender and StreamingTV for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/24ef4c72-fb52-45a4-b046-20af019edc84)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/ce38bbc8-dcf5-40f7-a169-a2745db5d286)
Churn rate
Males with No StreamingTV -  32.39%
Females with No StreamingTV – 34.70%

#### Distribution of Gender and StreamingMovies for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/66ae6d89-0589-4a7e-8826-8b7e1e32b5f6)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/5b8c769e-aeae-41a2-9276-46496fdfcc42)
Churn rate
Males with No StreamingMovies -  32.67%
Females with No StreamingMovies – 34.82%

#### Distribution of Gender and PaymentMethod for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/baa47966-f97b-4237-979f-3a6c491df135)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/648f2269-6789-40f1-b41d-3c002b3d145a)
Churn rate
Males with Electronic check -  45%
Females with Electronic check – 45.51%
Irrespective of gender, for the electronic check payment method, Males and Females both are high churners.

#### Distribution of Gender and PaperlessBilling for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/8131b0e5-69b7-455b-9988-e3f3c5b5becc)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/b8a81b4d-f5e2-48f8-93bc-87cf9406e956)
Churn rate
Males with PaperlessBilling – 33.65%
Females with PaperlessBilling – 33.52%

#### Distribution of SeniorCitizen and Dependents for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/3caf1bba-21f4-454a-9a2b-9ef4fdd9f640)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/5d7b2c0b-bb74-4710-9a04-6378997fdf79)
Churn rate
Independent Senior Citizen -  44.46%
Dependent Senior Citizen –  24.17%
Insight
Independent senior citizens exhibit a high propensity for churn, with a churn rate of 44%.

#### Distribution of SeniorCitizen and Partner for Churned and Non-Churned Customers
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/6fdb14c0-96b7-4c31-8925-4507e48a3231)
![image](https://github.com/nisu1906/EDA-Churn-Analysis/assets/150984180/a7752462-849b-427f-b298-070f0ab10db4)

Churn rate
Senior Citizen with Partner -  34.55%
Senior Citizen without Partner –  48.85%
Insight
48.85% of Senior citizens without partners are more prone to churn.

# Overall Insights
Senior citizens exhibit a higher likelihood of churn compared to other age groups.
Customers categorized as independent and without a partner are more susceptible to churn.
Customers with shorter tenure and month-to-month contracts are at a higher risk of churning.
There is a positive correlation between higher monthly charges and increased churn rates, while lower total charges also contribute to higher churn rates.
Females, especially within the first year of tenure (1-12 months), demonstrate a churn rate close to 50%, surpassing that of males.
Independent senior citizens without partners show a notably higher churn rate compared to younger age groups.








































































