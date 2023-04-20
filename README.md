# PANDAS  
Pandas is a powerful open-source data analysis and manipulation library for Python. It provides tools for data manipulation,     
cleaning, and analysis, including the ability to work with structured and unstructured data, and supports a wide range of data formats  N
such as CSV, Excel, SQL databases, and more.      

## DataFrame  
In Pandas, a DataFrame is a two-dimensional labeled data structure with columns of potentially different types, similar to a spreadsheet or    
SQL table. Here are some basic operations that you can perform on a DataFrame in Pandas:  

**Creating a DataFrame:**   
You can create a DataFrame by passing a dictionary of key-value pairs, where the keys represent the column names and the values represent the  
data for each column. Here is an example:   
```py
import numpy as np
import pandas as pd
dict1={
    'name':['harry','rohan','subh'],
    'marks':[90,99,23],
    'city':['banglore','ghy','mum']
}
df=pd.DataFrame(dict1) #it will create the data frame(convert into excelsheet)
df
```  
**OUTPUT**
|index|name|marks|city|
|---|---|---|---|
|0|harry|90|banglore|
|1|rohan|99|ghy|
|2|subh|23|mum|  


**Basic operation with data frame**
``` py  
df=pd.DataFrame(dict1) #it will create the data frame(convert into excelsheet)
df
df.to_csv("friends.csv") #gives the  excelsheet for data frame
df.to_csv("friends_no_index.csv",index=False) #for eliminating index
df.head(2) #first two rows will be shown
df.tail(2) #last two rows will be shown
df.describe()#it will do the statistical analysis with the numerics in data frame
murli=pd.read_csv("murli.csv")#to read the excel file
df['marks'][0]
df['marks'][0]=50
df.index=['first','second','third']
df.T # transpose operation
```
# Series  
In Pandas, a Series is a one-dimensional labeled array that can hold any data type such as integers, floats, strings, or even Python objects.  
It is similar to a column in a spreadsheet or a column in a SQL table.  
```py   
import pandas as pd
# create a series from a list
my_list = [10, 20, 30, 40, 50]
my_series = pd.Series(my_list)
print(my_series)
# access an element by its index label
print(my_series['b'])

# access multiple elements by their index labels
print(my_series[['a', 'c', 'e']])

# perform arithmetic operations on the series
my_series = my_series * 2
print(my_series)
```

# View and Copy concept in Pandas  
In Pandas, a view is a reference to the original data and a copy is a completely new and independent copy of the data. Understanding the difference   
between a view and a copy is important when working with large datasets, as it can affect performance and the results of your analysis.  

**1)** View:  
A view is a reference to the original data. When you create a view of a DataFrame, any changes made to the view will affect the original DataFrame.
Views are memory-efficient and can be useful when working with large datasets. Views can be created using the .loc and .iloc methods. Here is an example:  
```py  
import pandas as pd
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 35, 40],
        'City': ['New York', 'London', 'Paris', 'Tokyo']}
df = pd.DataFrame(data)
# Creating a view
view = df.loc[df['Age'] > 30]
# Modifying the view
view['City'] = 'Berlin'
print(df)
```
**2)** Copy:  
A copy is a completely new and independent copy of the data. When you create a copy of a DataFrame, any changes made to the copy will not affect the original DataFrame. Copies are memory-intensive and can be slower than views when working with large datasets. Copies can be created using the .copy() method. Here is an example:
```py  
import pandas as pd

data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 35, 40],
        'City': ['New York', 'London', 'Paris', 'Tokyo']}
df = pd.DataFrame(data)
# Creating a copy
copy = df.copy()
# Modifying the copy
copy['City'] = 'Berlin'
print(df)

