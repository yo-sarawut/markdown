+++
title = "Extracting rows using .iloc[]"
weight = 3
+++

Python is a great language for doing data analysis, primarily because of the fantastic ecosystem of data-centric Python packages.  **_Pandas_** is one of those packages and makes importing and analyzing data much easier.

Pandas provide a unique method to retrieve rows from a Data frame.  **`Dataframe.iloc[]`**  method is used when the index label of a data frame is something other than numeric series of 0, 1, 2, 3….n or in case the user doesn’t know the index label. Rows can be extracted using an imaginary index position which isn’t visible in the data frame.

> **Syntax:** pandas.DataFrame.iloc[]
> 
> **Parameters:**  
> **Index Position:** Index position of rows in integer or list of integer.
> 
> **Return type:** Data frame or Series depending on parameters
  

To download the CSV used in code, click  [here.](https://media.geeksforgeeks.org/wp-content/uploads/nba.csv)  

**Example 1:**  Extracting single row and comparing with .loc[]

In this example, same index number row is extracted by both .iloc[] and.loc[] method and compared. Since the index column by default is numeric, hence the index label will also be integers.  
```py
# importing pandas package 
import pandas as pd 

# making data frame from csv file 
data = pd.read_csv("nba.csv") 

# retrieving rows by loc method 
row1 = data.loc[3] 

# retrieving rows by iloc method 
row2 = data.iloc[3] 

# checking if values are equal 
row1 == row2 
```
**Output:**  
As shown in the output image, the results returned by both the methods are same.  
![](https://media.geeksforgeeks.org/wp-content/uploads/out1-23.jpg "Click to enlarge")

**Example #2:** Extracting multiple rows with index

In this example, multiple rows are extracted first by passing a list and then by passing integers to extract rows between that range. After that, both the values are compared.
```py
# importing pandas package 
import pandas as pd 

# making data frame from csv file 
data = pd.read_csv("nba.csv") 

# retrieving rows by loc method 
row1 = data.iloc[[4, 5, 6, 7]] 

# retrieving rows by loc method 
row2 = data.iloc[4:8] 

# comparing values 
row1 == row2 
```

**Output:**  
As shown in the output image, the results returned by both the methods are same. All values are True except values in college column since those were NaN values.

![](https://media.geeksforgeeks.org/wp-content/uploads/out2-16.jpg "Click to enlarge")


## Recommended Posts:

-   [Select Rows & Columns by Name or Index in Pandas DataFrame using [ ], loc & iloc](https://www.geeksforgeeks.org/select-rows-columns-by-name-or-index-in-pandas-dataframe-using-loc-iloc/?ref=rp)
-   [Python | Pandas Extracting rows using .loc[]](https://www.geeksforgeeks.org/python-pandas-extracting-rows-using-loc/?ref=rp)
-   [Select any row from a Dataframe using iloc[] and iat[] in Pandas](https://www.geeksforgeeks.org/select-any-row-from-a-dataframe-using-iloc-and-iat-in-pandas/?ref=rp)
-   [Python | Pandas Series.iloc](https://www.geeksforgeeks.org/python-pandas-series-iloc/?ref=rp)
-   [Difference between loc() and iloc() in Pandas DataFrame](https://www.geeksforgeeks.org/difference-between-loc-and-iloc-in-pandas-dataframe/?ref=rp)
-   [Python | Delete rows/columns from DataFrame using Pandas.drop()](https://www.geeksforgeeks.org/python-delete-rows-columns-from-dataframe-using-pandas-drop/?ref=rp)
-   [Select first or last N rows in a Dataframe using head() and tail() method in Python-Pandas](https://www.geeksforgeeks.org/select-first-or-last-n-rows-in-a-dataframe-using-head-and-tail-method-in-python-pandas/?ref=rp)
-   [How to skip rows while reading csv file using Pandas?](https://www.geeksforgeeks.org/how-to-skip-rows-while-reading-csv-file-using-pandas/?ref=rp)
-   [Concatenate strings from several rows using Pandas groupby](https://www.geeksforgeeks.org/concatenate-strings-from-several-rows-using-pandas-groupby/?ref=rp)
-   [Limited rows selection with given column in Pandas | Python](https://www.geeksforgeeks.org/limited-rows-selection-with-given-column-in-pandas-python/?ref=rp)
-   [How to randomly select rows from Pandas DataFrame](https://www.geeksforgeeks.org/how-to-randomly-select-rows-from-pandas-dataframe/?ref=rp)
-   [How to get rows/index names in Pandas dataframe](https://www.geeksforgeeks.org/how-to-get-rows-index-names-in-pandas-dataframe/?ref=rp)
-   [Get all rows in a Pandas DataFrame containing given substring](https://www.geeksforgeeks.org/get-all-rows-in-a-pandas-dataframe-containing-given-substring/?ref=rp)
-   [Different ways to iterate over rows in Pandas Dataframe](https://www.geeksforgeeks.org/different-ways-to-iterate-over-rows-in-pandas-dataframe/?ref=rp)
-   [Selecting rows in pandas DataFrame based on conditions](https://www.geeksforgeeks.org/selecting-rows-in-pandas-dataframe-based-on-conditions/?ref=rp)
-   [How to iterate over rows in Pandas Dataframe](https://www.geeksforgeeks.org/how-to-iterate-over-rows-in-pandas-dataframe/?ref=rp)
-   [Sorting rows in pandas DataFrame](https://www.geeksforgeeks.org/sorting-rows-in-pandas-dataframe/?ref=rp)
-   [Dealing with Rows and Columns in Pandas DataFrame](https://www.geeksforgeeks.org/dealing-with-rows-and-columns-in-pandas-dataframe/?ref=rp)
-   [Iterating over rows and columns in Pandas DataFrame](https://www.geeksforgeeks.org/iterating-over-rows-and-columns-in-pandas-dataframe/?ref=rp)
-   [Grouping Rows in pandas](https://www.geeksforgeeks.org/grouping-rows-in-pandas/?ref=rp)

> Reference : https://www.geeksforgeeks.org/python-extracting-rows-using-pandas-iloc/