+++
title = "Timestamp to Datetime"
weight = 5
+++
**Python timestamp to datetime and vice-versa**

>In this article, you will learn to convert timestamp to datetime object and datetime object to timestamp (with the help of examples).

It's pretty common to store date and time as a timestamp in a database. A Unix timestamp is the number of seconds between a particular date and January 1, 1970 at UTC.

----------

## Example 1: Python timestamp to datetime

```py
from datetime import datetime

timestamp = 1545730073
dt_object = datetime.fromtimestamp(timestamp)

print("dt_object =", dt_object)
print("type(dt_object) =", type(dt_object))
```

When you run the program, the output will be:
```text
 dt_object = 2018-12-25 09:27:53
type(dt_object) = <class 'datetime.datetime'> 
```
Here, we have imported  `datetime`  class from the  [datetime](https://www.programiz.com/python-programming/datetime)  module. Then, we used  `datetime.fromtimestamp()`  classmethod which returns the local date and time (datetime object). This object is stored in  dt_object  variable.

**Note:**  You can easily create a string representing date and time from a  `datetime`  object using  [strftime()](https://www.programiz.com/python-programming/datetime/strftime)  method.

----------

## Example 2: Python datetime to timestamp

You can get timestamp from a datetime object using  `datetime.timestamp()`  method.

```py
from datetime import datetime

# current date and time
now = datetime.now()

timestamp = datetime.timestamp(now)
print("timestamp =", timestamp)
```

> Reference : https://www.programiz.com/python-programming/datetime/timestamp-datetime