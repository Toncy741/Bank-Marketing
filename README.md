# Bank-Marketing


In the banking sector, direct marketing campaignS are a key method for

promoting financial products, particularly term deposits. These campaigns

rely heavily on phone calls to engage with potential customers. However,
 
predicting which clients will subscribe to a term deposit after a
  
marketing campaign remains a significant challenge. Customer decisions
  
are influenced by a variety of factors, including their demographics,
   
financial circumstances, and past interactions with the bank.


# Objective

To address this challenge, this project aims to develop a predictive

machine learning model using data from a Portuguese banking institution

The dataset, collected between May 2008 and November 2010, contains
 
detailed information from various direct marketing campaigns. It includes
 
attributes such as the customer’s age, job, marital status, education
  
level, and financial history, as well as details about the marketing
  
efforts, such as the number and outcome of previous contacts.

With a dataset that encompasses over 41,000 observations and 20 features,

this project will focus on identifying patterns and trends to predict

whether a customer will subscribe to a term deposit. By leveraging machine
 
learning algorithms, the goal is to improve the bank's ability to target
 
potential customers, optimize marketing resources, and increase campaign
  
success rates.

# Features

bank client data

1 - age (numeric)

2 - job : type of job (categorical: "admin.","unknown","unemployed","management","housemaid","entrepreneur","student",
                                   "blue-collar","self-employed","retired","technician","services")

3 - marital : marital status (categorical: "married","divorced","single"; note: "divorced" means divorced or widowed)

4 - education (categorical: "unknown","secondary","primary","tertiary")

5 - default: has credit in default? (binary: "yes","no")

6 - balance: average yearly balance, in euros (numeric)

7 - housing: has housing loan? (binary: "yes","no")

8 - loan: has personal loan? (binary: "yes","no")

# related with the last contact of the current campaign:

9 - contact: contact communication type (categorical: "unknown","telephone",
"cellular")

10 - day: last contact day of the month (numeric)

11 - month: last contact month of year (categorical: "jan", "feb", "mar", ..., "nov", "dec")

12 - duration: last contact duration, in seconds (numeric)

# other attributes:

13 - campaign: number of contacts performed d

# first step of this project

Importing necessary libraries:

- pandas (as pd) for data manipulation and analysis.
 
- numpy (as np) for numerical computations.
  
- matplotlib.pyplot (as plt) and seaborn (as sns) for data visualization.
 
- warnings to suppress warning messages.

# Loading the dataset

- The dataset is loaded from a CSV file named bank-full.csv using pd.read_csv(). The sep=';' parameter indicates that the CSV file uses semicolons as the delimiter.
  

* Printing the first 10 rows of the dataset:
  
- The head() function is used to display the first 10 rows of the dataset. This helps in understanding the structure and content of the data.

* Printing the last 10 rows of the dataset:
  
- The tail() function is used to display the last 10 rows of the dataset. This can be useful in identifying any patterns or anomalies at the end of the dataset.
  

- Renaming the 'y' column to 'subscription'
  
 The rename() function is used to rename the 'y' column to 'subscription'. The inplace=True parameter ensures that the changes are made directly to the original dataframe.

# Printing the column names

 The columns attribute is used to display the column names of the dataframe. The output shows that the 'y' column has been successfully renamed to 'subscription'.

# Printing the shape and size of the dataset

- The shape attribute is used to display the number of rows and columns in the dataset. The output shows that the dataset has 45,211 rows and 17 columns.
- The size attribute is used to display the total number of elements in the dataset. The output shows that the dataset has 768,587 elements.

# Printing the data types of each column:

- The dtypes attribute is used to display the data types of each column in the dataset. The output shows that the columns have a mix of integer (int64) and object (object) data types.

# Printing summary statistics for the dataset

- The describe() function is used to display summary statistics for the dataset, including count, mean, standard deviation, minimum, 25th percentile, median (50th percentile), 75th percentile, and maximum values. The output shows that the dataset has a wide range of values for each column.


