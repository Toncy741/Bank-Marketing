# Bank-Marketing


In the banking sector, direct marketing campaignS are a key method for

promoting financial products, particularly term deposits. These campaigns

rely heavily on phone calls to engage with potential customers. However,
 
predicting which clients will subscribe to a term deposit after a
  
marketing campaign remains a significant challenge. Customer decisions
  
are influenced by a variety of factors, including their demographics,
   
financial circumstances, and past interactions with the bank.


## Objective

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

## Features

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

## related with the last contact of the current campaign:

9 - contact: contact communication type (categorical: "unknown","telephone",
"cellular")

10 - day: last contact day of the month (numeric)

11 - month: last contact month of year (categorical: "jan", "feb", "mar", ..., "nov", "dec")

12 - duration: last contact duration, in seconds (numeric)

## other attributes:

13 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

14 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric, -1 means client was not previously contacted)

15 - previous: number of contacts performed before this campaign and for this client (numeric)

16 - poutcome: outcome of the previous marketing campaign (categorical: "unknown","other","failure","success")

Output variable (desired target)

17 - y - has the client subscribed a term deposit? (binary: "yes","no")


## first step of this project

Importing necessary libraries:

- pandas (as pd) for data manipulation and analysis.
 
- numpy (as np) for numerical computations.
  
- matplotlib.pyplot (as plt) and seaborn (as sns) for data visualization.
 
- warnings to suppress warning messages.

## Loading the dataset

- The dataset is loaded from a CSV file named bank-full.csv using pd.read_csv(). The sep=';' parameter indicates that the CSV file uses semicolons as the delimiter.
  

* Printing the first 10 rows of the dataset:
  
- The head() function is used to display the first 10 rows of the dataset. This helps in understanding the structure and content of the data.

* Printing the last 10 rows of the dataset:
  
- The tail() function is used to display the last 10 rows of the dataset. This can be useful in identifying any patterns or anomalies at the end of the dataset.
  

- Renaming the 'y' column to 'subscription'
  
 The rename() function is used to rename the 'y' column to 'subscription'. The inplace=True parameter ensures that the changes are made directly to the original dataframe.

## Printing the column names

 The columns attribute is used to display the column names of the dataframe. The output shows that the 'y' column has been successfully renamed to 'subscription'.

## Printing the shape and size of the dataset

- The shape attribute is used to display the number of rows and columns in the dataset. The output shows that the dataset has 45,211 rows and 17 columns.
- The size attribute is used to display the total number of elements in the dataset. The output shows that the dataset has 768,587 elements.

## Printing the data types of each column:

- The dtypes attribute is used to display the data types of each column in the dataset. The output shows that the columns have a mix of integer (int64) and object (object) data types.

## Printing summary statistics for the dataset

- The describe() function is used to display summary statistics for the dataset, including count, mean, standard deviation, minimum, 25th percentile, median (50th percentile), 75th percentile, and maximum values. The output shows that the dataset has a wide range of values for each column.

## Printing information about the dataset

- The info() function is used to display information about the dataset, including the number of entries, data types, and memory usage. The output shows that the dataset has 45,211 entries, 17 columns, and a mix of integer (int64) and object (object) data types.

## Checking for null values

- The isnull().sum() function is used to display the number of null values in each column. The output shows that there are no null values in any of the columns.

## Finding features with one value

- A for loop is used to iterate over each column in the dataset and print the number of unique values in each column using the nunique() function. The output shows that each column has a varying number of unique values, ranging from 2 (default, housing, loan, subscription) to 7,168 (balance).

## Printing categorical columns

- A list comprehension is used to identify the categorical columns in the dataset by checking the data type of each column. The output shows that there are 10 categorical columns.

## Printing a few rows of the categorical columns

- The head() function is used to display the first few rows of the categorical columns. The output shows the values for each categorical column.

## Quickly identifying the number of distinct categories for each categorical feature

- A for loop is used to iterate over each categorical feature and print the number of unique categories using the unique() function. The output shows the number of categories for each feature, ranging from 2 (default, housing, loan, subscription) to 12 (job, month).


Plotting all categorical variables with different colors:
- The select_dtypes() function is used to select only the categorical columns from the dataset.
- A for loop is used to iterate over each categorical column and create a count plot using sns.countplot(). The palette parameter is used to apply a color palette to the plot.
- The title() function is used to set the title of the plot, and the xticks() function is used to rotate the x-axis labels for better readability.

## Pie diagram for subscription proportion

- The value_counts() function is used to count the number of occurrences of each unique value in the 'subscription' column.
  
- The plot.pie() function is used to create a pie chart of the subscription proportion. The autopct parameter is used to display the percentage value of each slice, and the colors parameter is used to specify the colors of the slices.
  
- The title() function is used to set the title of the plot, and the ylabel() function is used to remove the y-axis label.

## Finding the relationship between categorical features and the target variable (subscription)

- A list of categorical features is defined, and a for loop is used to iterate over each feature.
  
- For each feature, a count plot is created using sns.countplot(), with the feature on the x-axis and the target variable ('subscription') as the hue.
  
- The title() function is used to set the title of the plot, and the xticks() function is used to rotate the x-axis labels for better readability.

## Checking counts of target variable split by each categorical feature:

- A for loop is used to iterate over each categorical feature.
 
- For each feature, the groupby() function is used to group the data by the feature and the target variable ('subscription'), and the size() function is used to count the number of occurrences in each group.
  
- The unstack() function is used to reshape the data into a pivot table, and the fillna(0) function is used to replace missing values with 0.
- The resulting counts are printed to the console.

## Exploring numerical features

- A list comprehension is used to identify the numerical features in the dataset by checking the data type of each column.
  
-  The dtypes attribute is used to check if the data type is not 'O' (object), and the feature not in ['deposit'] condition is used to exclude the 'deposit' column.
  
- The length of the numerical_features list is printed to the console, indicating that there are 7 numerical variables in the dataset.
  
- The head() function is used to display the first few rows of the numerical features.

## Finding discrete numerical features

- A list comprehension is used to identify the discrete numerical features in the dataset by checking if the number of unique values in each feature is less than 25.
  
- The length of the discrete_feature list is printed to the console, indicating that there are 0 discrete variables in the dataset.

## Plotting histograms for numerical variables
- The select_dtypes() function is used to select only the numerical columns from the dataset.
  
- A for loop is used to iterate over each numerical column and create a histogram using sns.histplot(). The kde=True parameter is used to display the kernel density estimate (KDE) of the distribution, and the color parameter is used to specify the color of the histogram.
  
- The title() function is used to set the title of the plot, and the show() function is used to display the plot.


## Boxplots for each numerical feature against subscription

- A list of numerical columns is defined, and a for loop is used to iterate over each column.
  
- For each column, a boxplot is created using sns.boxplot() to visualize the distribution of the column against the subscription outcome.
  
- The title() function is used to set the title of the plot, and the show() function is used to display the plot.

## Handling outliers

- A list of numerical columns is defined, and a for loop is used to iterate over each column.
  
- For each column, the 25th percentile (Q1) and 75th percentile (Q3) are calculated using the quantile() function.
  
- The interquartile range (IQR) is calculated as the difference between Q3 and Q1.
  
- The lower and upper bounds for detecting outliers are defined as Q1 - 1.5IQR and Q3 + 1.5IQR, respectively.
  
- The outliers are identified and removed from the dataset using boolean indexing.
  
- A new boxplot is created using sns.boxplot() to visualize the distribution of the column against the subscription outcome without outliers.
- The count of removed outliers is printed to the console

## Converting categorical data to numerical data using LabelEncoder

- The LabelEncoder class from scikit-learn is imported and initialized.
  
- The fit_transform() method is used to apply label encoding to each categorical column in the dataset. This converts the categorical values into numerical values
  
- The encoded columns are assigned back to the original dataframe.

## Printing the first 10 rows after encoding

- The head() function is used to display the first 10 rows of the encoded dataframe.

## Removing rows where pdays contains -inf

- The df dataframe is filtered to remove rows where the 'pdays' column contains -inf values.
  
- The resulting dataframe is assigned back to the df variable.

## Removing all rows with NaN values

- The dropna() function is used to remove all rows with NaN values from the df dataframe
  
- The resulting dataframe is assigned to a new variable df_cleaned.

## Calculating the correlation matrix

- The corr() function is used to calculate the correlation matrix of the dataframe. This produces a square matrix where each entry represents the correlation coefficient between two variables.

## Creating a correlation heatmap

- The correlation matrix is assigned to a variable correlation_matrix.
  
- A heatmap is created using sns.heatmap() to visualize the correlation matrix. The annot=True parameter is used to display the correlation coefficients on the
  
heatmap, and the cmap='coolwarm' parameter is used to specify the color scheme. The fmt='.2f' parameter is used to format the correlation coefficients to two

decimal places, and the linewidths=0.5 parameter is used to add a small gap between the cells.
  
- The title() function is used to set the title of the plot, and the show() function is used to display the plot.

## Understanding the relationship between different variables

- A list of numerical columns is defined, and the pairplot() function from Seaborn is used to create a pair plot of the selected columns. This plot shows the distribution of each variable and the relationships between each pair of variables.
  
- The show() function is used to display the plot.  


