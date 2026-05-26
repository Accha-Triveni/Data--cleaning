# Data--cleaning
Data Immersion &amp; Wrangling focuses on understanding and preparing the dataset for analysis through data exploration, quality assessment, cleaning, and transformation. It involves handling missing values, duplicates, inconsistent formatting, and outliers to create a clean, structured, and analysis-ready dataset using Python/Pandas.
# Dataset are:
.Dataset Name (Original File): sales_data (1).csv
.Dataset Name (Cleaned Version): cleaned_sales_data.csv
# Issues found and fixed
Issue Type	Identified Problem	Solution Applied (Pandas Code)	Impact / Result
Duplicate Records	Duplicate rows present in the raw data.	df.drop_duplicates()	Cleaned out redundant rows to ensure unique transactions.
Missing Values (Age)	1 missing value in the customer age column.	df['Age'].fillna(df['Age'].mean())	Replaced missing values with the dataset's average age (≈44.22).
Missing Values (Price)	1 missing value in the product price column.	df['Price'].fillna(df['Price'].median())	Replaced missing values with the median price (300.0).
Missing Values (Rating)	2 missing values in customer satisfaction ratings.	df['Rating'].fillna(df['Rating'].mode()[0])	Replaced missing values with the most frequently occurring rating (mode).
Outliers / Invalid Data	Maximum age was recorded as 150, which is biologically impossible.	df = df[df['Age'] < 100]	Filtered out rows containing unrealistic age entries.
Inconsistent Dates	Order_Date had mixed formats (e.g., 2024-01-12, 2024/01/17, 20-01-2024).	pd.to_datetime(df['Order_Date'], errors='coerce')	Standardized everything into a uniform timestamp format (unresolvable dates turned to NaN).
# newly added columns
Data columns (total 15 columns):
 #   Column          Non-Null Count  Dtype  
---  ------          --------------  -----  
...
 12  Total_Amount    8 non-null      float64
 13  Month           6 non-null      float64
 14  Age_Group       8 non-null      object
 # Tools used
 .Python3
 .Numpy
 .Pandas
 
