+++
title = "Basics to Beyond"
weight = 1
+++

>  A tutorial walkthrough of Python Pandas Library

![enter image description here](https://iqrablogger.com/wp-content/uploads/2020/03/574-5747046_python-pandas-logo-transparent-hd-png-download.png)

For those of you who are getting started with Machine learning, just like me, would have come across Pandas,  _the data analytics library_. In the rush to understand the gimmicks of ML, we often fail to notice the importance of this library. But soon you will hit a roadblock where you would need to play with your data, clean and perform data transformations before feeding it into your ML model.

Why do we need this blog when there are already a lot of documentation and tutorials? Pandas, unlike most python libraries, has a steep learning curve. The reason is that you need to understand your data well in order to apply the functions appropriately. Learning Pandas syntactically is not going to get you anywhere. Another problem with Pandas is that there is that there is more than one way to do things. Also, when I started with Pandas it’s extensive and elaborate documentation was overwhelming. I checked out the  [cheatsheets](https://www.google.com/search?q=pandas%20cheetsheets&oq=pandas%20cheetsheets&aqs=chrome..69i57.3801j0j7&sourceid=chrome&ie=UTF-8&ref=hackernoon.com)  and that scared me even more.

In this blog, I am going to take you through Pandas functionalities by cracking specific use cases that you would need to achieve with a given data.

### Setup and Installation

Before we move on with the code for understanding the features of Pandas, let’s get Pandas installed in your system. I advise you to create a virtual environment and install Pandas inside the virtualenv.

#### Create virtualenv

```python
virtualenv -p python3 venv
source venv/bin/activate
```

#### Install Pandas

```python
pip install pandas
```

#### Jupyter Notebook

If you are learning Pandas, I would advise you to dive in and use a jupyter notebook for the same. The visualization of data in jupyter notebooks makes it easier to understand what is going on at each step.

```python
pip install jupyter
jupyter notebook
```

Jupyter by default runs in your system-wide installation of python. In order to run it in your virtualenv follow the link and create a user level kernel  [https://anbasile.github.io/programming/2017/06/25/jupyter-venv/](https://anbasile.github.io/programming/2017/06/25/jupyter-venv/?ref=hackernoon.com)

### Sample Data

I created a simple purchase order data. It comprises of sales data of each salesperson of a company over countries and their branches at different regions in each country.  [Here is a link to the spreadsheet for you to download.](http://region/%09Sales%20Person%09Date%20of%20Purchase%09Total%09Quantity%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%202%20India%09North%09John%098/1/2011%200:00:00%09100000%09567%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%203%20US%09North%09Bill%0912/26/2011%200:00:00%09120000%093000%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%204%20UK%09North%09Thomas%098/6/2015%200:00:00%09140000%09345%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%205%20Australia%09East%09John%091/8/2010%200:00:00%09160000%091000%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%206%20Africa%09East%09Bill%097/15/2010%200:00:00%09180000%09123%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%207%20Singapore%09East%09Thomas%093/29/2012%200:00:00%09200000%091000%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%208%20Mylasia%09West%09John%0912/30/2013%200:00:00%091000000%097890%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%209%20India%09West%09Bill%094/8/2016%200:00:00%09240000%09200%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2010%20US%09West%09Thomas%099/4/2018%200:00:00%0926000000%091000%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2011%20UK%09North%09John%095/19/2015%200:00:00%09100000%091000%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2012%20Australia%09North%09Bill%094/15/2012%200:00:00%09120000%09567%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2013%20Africa%09North%09Thomas%098/11/2015%200:00:00%09140000%091000%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2014%20Singapore%09East%09John%095/9/2017%200:00:00%09160000%09892%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2015%20Mylasia%09East%09Bill%0912/13/2013%200:00:00%09180000%09444%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2016%20India%09East%09Thomas%093/3/2013%200:00:00%09200000%0990%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2017%20US%09West%09John%098/26/2015%200:00:00%09220000%0990%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2018%20UK%09West%09Bill%094/13/2012%200:00:00%09240000%0990%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2019%20Australia%09West%09Thomas%096/28/2013%200:00:00%09260000%0990%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2020%20Africa%09North%09John%0910/5/2012%200:00:00%09140000%0985%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2021%20Singapore%09North%09Bill%091/7/2016%200:00:00%09150000%0985%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%09%2022?ref=hackernoon.com)

![](https://hackernoon.com/hn-images/1*kA0O7fuDrvoE8K_zfvWaqw.png)

### Load data into Pandas

With Pandas, we can load data from different sources. Few of them are loading from CSV or a remote URL or from a database. The loaded data is stored in a Pandas data structure called DataFrame. DataFrame’s are usually refered by the variable name df . So, anytime you see df from here on you should be associating it with Dataframe.

#### From CSV File

```python
import pandas
df = pandas.read_csv("path_to_csv")
```

#### From Remote URL

You can pass a remote URL to the CSV file in read_csv.

```python
import pandas
df = pandas.read_csv("remote/url/path/pointing/to/csv")
```

#### From DB

In order to read from Database, read the data from DB into a python list and use DataFrame() to create one

```python
db = # Create DB connection object 
cur = db.cursor()
cur.execute("SELECT * FROM <TABLE>")
df = pd.DataFrame(cur.fetchall())
```

Each of the above snippets reads data from a source and loads it into Pandas’ internal data structure called DataFrame

### Understanding Data

Now that we have the Dataframe ready let’s go through it and understand what’s inside it

```python
# 1. shows you a gist of the data
df.head()
```

```python
# 2. Some statistical information about your data
df.describe()
```

```python
# 3. List of columns headers
df.columns.values
```

![](https://hackernoon.com/hn-images/1*XJDBjuBY4LK-VyKq2HDNUw.png)

### Pick & Choose your Data

Now that we have loaded our data into a DataFrame and understood its structure, let’s pick and choose and perform visualizations on the data. When it comes to selecting your data, you can do it with both Indexesor based on certain conditions. In this section, let’s go through each one of these methods.

#### Indexes

Indexes are labels used to refer to your data. These labels are usually your column headers. For eg., Country, Region, Quantity Etc.,

#### Selecting Columns

```python
# 1. Create a list of columns to be selected
columns_to_be_selected = ["Total", "Quantity", "Country"]
```

```python
# 2. Use it as an index to the DataFrame
df[columns_to_be_selected]
```

```python
# 3. Using loc method
df.loc[columns_to_be_selected]
```

![](https://hackernoon.com/hn-images/1*Fes_TGhxHtR-4Xktq8-opw.png)

#### Selecting Rows

Unlike the columns, our current DataFrame does not have a label which we can use to refer the row data. But like arrays, DataFrame provides numerical indexing(0, 1, 2…) by default.

```python
# 1. using numerical indexes - iloc
df.iloc[0:3, :]
```

```python
# 2. using labels as index - loc
row_index_to_select = [0, 1, 4, 5]
df.loc[row_index_to_select]
```

![](https://hackernoon.com/hn-images/1*faazKZaQGHnckMhM8XrG4A.png)

#### Filtering Rows

Now, in a real-time scenario, you would most probably not want to select rows based on an index. An actual real-life requirement would be to filter out the rows that satisfy a certain condition. With respect to our dataset, we can filter by any of the following conditions

```python
1. Total sales > 200000
df[df["Total"] > 200000]
```

```python
2. Total sales > 200000 and in UK
df[(df["Total"] > 200000) & (df["Country"] == "UK")]
```

### Playing With Dates

Most of the times when dealing with date fields we don’t use them as it is. Pandas make it really easy for you to project Date/Month/Year from it and perform operations on top of it

In our sample dataset, the Date_of_purchase is of type string, hence the first step would be to convert them to the DateTime type.

```python
>>> type(df['Date of Purchase'].iloc[0])
str
```

#### Converting Column to DateTime Object

```python
>>> df['Date of Purchase'] = pd.to_datetime(df['Date of Purchase'])
>>> type(df['Date of Purchase'].iloc[0])
pandas._libs.tslibs.timestamps.Timestamp
```

**Extracting Date, Month & Year**

```python
df['Date of Purchase'].dt.date    # 11-09-2018
df['Date of Purchase'].dt.day     # 11
df['Date of Purchase'].dt.month   # 09
df['Date of Purchase'].dt.year    # 2018
```

### Grouping

#### Statistical operations

You can perform statistical operations such as min, max, mean etc., over one or more columns of a Dataframe.

```python
df["Total"].sum()
df[["Total", "Quantity"]].mean()
df[["Total", "Quantity"]].min()
df[["Total", "Quantity"]].max()
df[["Total", "Quantity"]].median()
df[["Total", "Quantity"]].mode()
```

Now in a real-world application, the raw use of these statistical functions are rare, often you might want to group data based on specific parameters and derive a gist of the data.

Let’s look at an example where we look at the country-wise, country & Region-wise sales.

```python
# 1. Country wise sales and Quantity
df.groupby("Country").sum()
```

```python
# 2. Quantity of sales over each country & Region
df.groupby(["Country", "Region"])["Quantity"].sum()
```

```python
# 3. More than one aggregation
df.groupby(["Country", "Region"]).agg(
                     {'Total':['sum', 'max'], 
                      'Quantity':'mean'})
```

![](https://hackernoon.com/hn-images/1*tib5Q6c4SzDbtGq_XnTt8A.png)

### Pivot Table

Pivot Table is an advanced version of groupby, where you can stack dimensions over both rows and columns. i.e., as the data grows the groupby above is going to grow in length and will become hard to derive insights, hence a well-defined way to look at it would be Pivot tables

```python
import numpy as np
df.pivot_table(index=["Country"], 
               columns=["Region"], 
               values=["Quantity"], 
               aggfunc=[np.sum])
```

![](https://hackernoon.com/hn-images/1*bHLja1_fsEsRUtMjOcg3iQ.png)

Another advantage of the Pivot Table is that you can add as many dimensions and functions you want. It also calculates a grand total value for you

```python
import numpy as np
df.pivot_table(index=["Country"], 
               columns=["Region","Requester"], 
               values=["Quantity"], 
               aggfunc=[np.sum], 
               margins=True,
               margins_name="Grand Total")
```

![](https://hackernoon.com/hn-images/1*iRd4MKEk4hElhE3UXABq3g.png)

Okay, that was a lot of information in 5 minutes. Take some time in trying out the above exercises. In the next blog, I will walk you through some more deeper concepts and magical visualizations that you can create with Pandas.

Every time you start learning Pandas, there is a good chance that you may get lost in the Pandas jargons like index, functions, numpy etc., But don’t let that get to you. What you really have to understand is that Pandas is a tool to visualize and get a deeper understanding of your data.

With that mindset take a sample dataset from your spreadsheet and try deriving some insights out of it. Share what you learn.  [Here is the link to my jupyter notebook for you to get started.](https://github.com/bhavaniravi/pandas_tutorial/blob/master/Pandas_Basics_To_Beyond.ipynb?ref=hackernoon.com)

**_Did the blog nudge a bit to give Pandas another chance?_**  
_Hold the “claps” icon and give a shout out to me on_ [_twitter_](https://twitter.com/@bhavaniravi?ref=hackernoon.com)_. Follow to stay tuned on future blogs_


>Reference : [https://hackernoon.com](https://hackernoon.com/python-pandas-tutorial-92018da85a33)