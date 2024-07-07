Q1. Create a Pandas Series that contains the following data: 4, 8, 15, 16, 23, and 42. Then, print the series.
python
Copy code
import pandas as pd

# Create a Pandas Series
series = pd.Series([4, 8, 15, 16, 23, 42])

# Print the series
print(series)
Output:

go
Copy code
0     4
1     8
2    15
3    16
4    23
5    42
dtype: int64
Q2. Create a variable of list type containing 10 elements in it, and apply pandas.Series function on the variable print it.
python
Copy code
import pandas as pd

# Create a list variable
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Create a Pandas Series from the list
series = pd.Series(my_list)

# Print the series
print(series)
Output:

go
Copy code
0     1
1     2
2     3
3     4
4     5
5     6
6     7
7     8
8     9
9    10
dtype: int64
Q3. Create a Pandas DataFrame that contains the following data:
Name	Age	Gender
Emma	28	Female
Daniel	35	Male
Sophie	21	Female
Jack	29	Male
Then, print the DataFrame.

python
Copy code
import pandas as pd

# Create a dictionary with the data
data = {
    'Name': ['Emma', 'Daniel', 'Sophie', 'Jack'],
    'Age': [28, 35, 21, 29],
    'Gender': ['Female', 'Male', 'Female', 'Male']
}

# Create a Pandas DataFrame
df = pd.DataFrame(data)

# Print the DataFrame
print(df)
Output:

markdown
Copy code
     Name  Age  Gender
0    Emma   28  Female
1  Daniel   35    Male
2  Sophie   21  Female
3    Jack   29    Male
Q4. What is ‘DataFrame’ in pandas and how is it different from pandas.Series? Explain with an example.
DataFrame: A DataFrame in Pandas is a 2-dimensional labeled data structure with columns of potentially different types. It is similar to a table in a relational database or an Excel spreadsheet.

Series: A Series in Pandas is a one-dimensional labeled array capable of holding data of any type (integer, string, float, etc.).

Example:

Series Example:

python
Copy code
import pandas as pd

# Creating a Series
series = pd.Series([10, 20, 30, 40, 50])

# Printing the Series
print(series)
Output:

go
Copy code
0    10
1    20
2    30
3    40
4    50
dtype: int64
DataFrame Example:

python
Copy code
import pandas as pd

# Creating a DataFrame
data = {
    'Name': ['John', 'Emma', 'Michael'],
    'Age': [30, 28, 35],
    'City': ['New York', 'Chicago', 'Los Angeles']
}

df = pd.DataFrame(data)

# Printing the DataFrame
print(df)
Output:

markdown
Copy code
     Name  Age         City
0     John   30     New York
1     Emma   28     Chicago
2  Michael   35  Los Angeles
Difference:

A Series is a single column of data with an index. It represents a single attribute or feature.
A DataFrame is a collection of Series objects put together to share the same index. It represents a table of data with rows and columns, where each column is a Series.
Q5. What are some common functions you can use to manipulate data in a Pandas DataFrame? Can you give an example of when you might use one of these functions?
Common functions to manipulate data in a Pandas DataFrame include:

Filtering: Selecting rows based on conditions.
Sorting: Sorting rows by one or more columns.
Grouping: Aggregating data based on some criteria.
Merging: Combining multiple DataFrames based on a key.
Pivoting: Reshaping data from long to wide format.
Example of filtering data:

python
Copy code
# Example: Filtering data in a DataFrame
import pandas as pd

# Sample DataFrame
data = {
    'Name': ['John', 'Emma', 'Michael', 'Sophie', 'David'],
    'Age': [30, 28, 35, 25, 32],
    'City': ['New York', 'Chicago', 'Los Angeles', 'San Francisco', 'Seattle']
}

df = pd.DataFrame(data)

# Filter for people aged 30 and above
filtered_df = df[df['Age'] >= 30]

print(filtered_df)
Output:

markdown
Copy code
      Name  Age         City
0     John   30     New York
2  Michael   35  Los Angeles
4    David   32      Seattle
Q6. Which of the following is mutable in nature Series, DataFrame, Panel?
Series: Immutable (values can be changed, but size and index labels cannot be changed).
DataFrame: Mutable (you can modify values, add or delete columns, etc.).
Panel: Deprecated in recent versions of Pandas. Previously, it was mutable.
Q7. Create a DataFrame using multiple Series. Explain with an example.
python
Copy code
import pandas as pd

# Creating Series
s1 = pd.Series([10, 20, 30, 40], name='A')
s2 = pd.Series([1, 2, 3, 4], name='B')
s3 = pd.Series(['a', 'b', 'c', 'd'], name='C')

# Creating DataFrame using Series
df = pd.DataFrame([s1, s2, s3])

# Transpose the DataFrame if needed
df = df.T

# Print the DataFrame
print(df)
Output:

css
Copy code
    A  B  C
0  10  1  a
1  20  2  b
2  30  3  c
3  40  4  d
In this example:

Three Series (s1, s2, s3) are created.
These Series are combined into a DataFrame df using the pd.DataFrame() constructor.
The DataFrame is transposed (df.T) to have columns A, B, and C as intended.
Each Series becomes a column in the resulting DataFrame. This method allows you to create a DataFrame from existing Series, which can be useful when you have data organized into Series format and want to combine them into a single DataFrame.
