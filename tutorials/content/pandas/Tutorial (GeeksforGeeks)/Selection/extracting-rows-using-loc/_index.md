+++
title = "Extracting rows using .loc[]"
weight = 2
+++
**Pandas Extracting rows using .loc[]**

Python is a great language for doing data analysis, primarily because of the fantastic ecosystem of data-centric Python packages.  **_Pandas_**  is one of those packages and makes importing and analyzing data much easier.

Pandas provide a unique method to retrieve rows from a Data frame.  **`DataFrame.loc[]`**  method is a method that takes only index labels and returns row or dataframe if the index label exists in the caller data frame.

> **Syntax:** pandas.DataFrame.loc[]
> 
> **Parameters:**  
> **Index label:** String or list of string of index label of rows
> 
> **Return type:** Data frame or Series depending on parameters


To download the CSV used in code, click  [here.](https://media.geeksforgeeks.org/wp-content/uploads/nba.csv)  

**Example #1:**  Extracting single Row

In this example, Name column is made as the index column and then two single rows are extracted one by one in the form of series using index label of rows.  

```py
# importing pandas package 
import pandas as pd 

# making data frame from csv file 
data = pd.read_csv("nba.csv", index_col ="Name") 

# retrieving row by loc method 
first = data.loc["Avery Bradley"] 
second = data.loc["R.J. Hunter"] 

print(first, "\n\n\n", second) 
```
**Output:**  
As shown in the output image, two series were returned since there was only one parameter both of the times.  
![](https://media.geeksforgeeks.org/wp-content/uploads/out1-22.jpg "Click to enlarge")

  
**Example #2:** Multiple parameters

In this example, Name column is made as the index column and then two single rows are extracted at the same time by passing a list as parameter.
```py
# importing pandas package 
import pandas as pd 

# making data frame from csv file 
data = pd.read_csv("nba.csv", index_col ="Name") 

# retrieving rows by loc method 
rows = data.loc[["Avery Bradley", "R.J. Hunter"]] 

# checking data type of rows 
print(type(rows)) 

# display 
rows 
```
**Output:**  
As shown in the output image, this time the data type of returned value is a data frame. Both of the rows were extracted and displayed like a new data frame.  
![](https://media.geeksforgeeks.org/wp-content/uploads/out2-15.jpg "Click to enlarge")

  

  

**Example #3:** Extracting multiple rows with same index

In this example, Team name is made as the index column and one team name is passed to .loc method to check if all values with same team name have been returned or not.
```py
# importing pandas package 
import pandas as pd 

# making data frame from csv file 
data = pd.read_csv("nba.csv", index_col ="Team") 

# retrieving rows by loc method 
rows = data.loc["Utah Jazz"] 

# checking data type of rows 
print(type(rows)) 

# display 
rows 
```
**Output:**  
As shown in the output image, All rows with team name “Utah Jazz” were returned in the form of a data frame.  
![](https://media.geeksforgeeks.org/wp-content/uploads/out3-11.jpg "Click to enlarge")

**Example #4:** Extracting rows between two index labels

In this example, two index label of rows are passed and all the rows that fall between those two index label have been returned (Both index labels Inclusive).
```py
# importing pandas package 
import pandas as pd 

# making data frame from csv file 
data = pd.read_csv("nba.csv", index_col ="Name") 

# retrieving rows by loc method 
rows = data.loc["Avery Bradley":"Isaiah Thomas"] 

# checking data type of rows 
print(type(rows)) 

# display 
rows 
```
**Output:**  
As shown in the output image, all the rows that fall between passed two index labels are returned in the form of a data frame.  
![](https://media.geeksforgeeks.org/wp-content/uploads/out4-5.jpg "Click to enlarge")

  
  

  

## Recommended Posts:

-   [Select Rows & Columns by Name or Index in Pandas DataFrame using [ ], loc & iloc](https://www.geeksforgeeks.org/select-rows-columns-by-name-or-index-in-pandas-dataframe-using-loc-iloc/?ref=rp)
-   [Python | Extracting rows using Pandas .iloc[]](https://www.geeksforgeeks.org/python-extracting-rows-using-pandas-iloc/?ref=rp)
-   [Python | Pandas Series.loc](https://www.geeksforgeeks.org/python-pandas-series-loc/?ref=rp)
-   [Python | Pandas DataFrame.loc[]](https://www.geeksforgeeks.org/python-pandas-dataframe-loc/?ref=rp)
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

> Reference : https://www.geeksforgeeks.org/python-pandas-extracting-rows-using-loc/?ref=lbp