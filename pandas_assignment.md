# PandasAssignment

---

### Q1. How do you load a CSV file into a Pandas DataFrame?
A) First we need to import pandas and with **pd.read_csv** command we can load the csv file.

```
import pandas as pd

df = pd.read_csv("./data.csv")
df

```

---

### Q2. How do you check the data type of a column in a Pandas DataFrame?
A) To check the data type in pandas DataFrame we can use the **dtypes** attribute. The attribute returns a series with the data type of each column.

```
df.dtypes

output:
Duration      int64
Pulse         int64
Maxpulse      int64
Calories    float64
dtype:      object

```
---

### Q3. How do you select rows from a Pandas DataFrame based on a condition?
A) Based on columns values we will select rows from a pandas DataFrame based on condition.
In the below example 'Name', 'Age', 'Stream', 'Percentage' are columns, using greater than condition we 
are fetching the rows.

```
import pandas as pd

record = {
  
 'Name': ['Ankit', 'Amit', 'Aishwarya', 'Priyanka', 'Priya', 'Shaurya' ],
 'Age': [21, 19, 20, 18, 17, 21],
 'Stream': ['Math', 'Commerce', 'Science', 'Math', 'Math', 'Science'],
 'Percentage': [88, 92, 95, 70, 65, 78] }


#creating dataframe
df_1 = pd.DataFrame(record, columns = ['Name','Age','Stream','Percentage'])


# selecting rows based on condition
rslt_df = df_1[ df_1 ['Percentage'] > 80 ]
rslt_df

output :
    Name	    Age	    Stream	    Percentage
	-------------------------------------------------
0	Ankit	    21	    Math	     88
1	Amit	    19	    Commerce	 92
2	Aishwarya   20	    Science	     95

```
---

### Q4. How do you rename columns in a Pandas DataFrame?
A) By using **rename()** method we can rename the columns in Pandas DataFrame.

```
print(df)

output:
	Duration	Pulse	Maxpulse	Calories
    ------------------------------------------------------
0	60	        110	    130	        409.1
1	60	        117	    145	        479.0
2	60	        103	    135	        340.0
3	45	        109	    175	        282.4
4	45	        117	    148	        406.0

```

```
using column index we can rename and by specifying the column name itself we can sepcify

df.rename(columns = {df.columns[0]:"DURATION"})
df.rename(columns = {"Duration":"DURATION", "Pulse":"PULSE"})

output : 

	DURATION   PULSE    Maxpulse	Calories
    ----------------------------------------------------
0	    60	    110	    130	        409.1
1	    60	    117	    145	        479.0
2	    60	    103	    135	        340.0
3	    45	    109	    175	        282.4
4	    45	    117	    148	        406.0

```
---

### Q5. How do you drop columns in a Pandas DataFrame?
A) Using drop() method we can delete the columns. 


```
print(df)


output:
	Duration	Pulse	  Maxpulse	Calories
    -----------------------------------------------------
0	60	        110	    130	        409.1
1	60	        117	    145	        479.0
2	60	        103	    135	        340.0
3	45	        109	    175	        282.4
4	45	        117	    148	        406.0

```

```
axis: int or string value, 0 ???index??? for Rows and 1 ???columns??? for Columns.
df.drop("Maxpulse", axis = 1)
print(df)

output:

	Duration	Pulse	    Calories
    -----------------------------------------
0	60	        110	      409.1
1	60	        117	      479.0
2	60	        103	      340.0
3	45	        109	      282.4
4	45	        117	      406.0
```

---

### Q6. How do you find the unique values in a column of a Pandas DataFrame?
A) By using **unique()** method, we can find the unique values in a column of a Pandas DataFrame.

```
data = {
    'A':[1, 2, 3, 4, 5], 
    'B':[6, 6, 8, 9, 10], 
    'C':[6, 6, 6, 6, 6], 
    'D':[7, 8, 9, 9, 9], 
    'E':[8, 9, 7, 8, 9] }

#create a data frame
df = pd.DataFrame(data)

# to get unique values of B
df.B.unique()

output : array([ 6,  8,  9, 10], dtype=int64)

```
---

### Q7. How do you find the number of missing values in each column of a Pandas DataFrame?
A) Using **isnull()** detect missing values in the given object and to find the count of number of missing values we can use **sum()** . 

---

### Q8. How do you fill missing values in a Pandas DataFrame with a specific value?
A) The fillna() function iterates through  dataset and fills all empty rows with a specified value.

---

### Q9. How do you concatenate two Pandas DataFrames?
A) The concat() function in pandas is used to append either columns or rows from one DataFrame to another. 

---

### Q10. How do you merge two Pandas DataFrames on a specific column?
A) To merge two Pandas DataFrames on a specific column, you can use the **merge()** function. This function will take two DataFrames as arguments and a on keyword argument, which specifies the name of the column that you want to merge the DataFrames on. 

```
For example, suppose you have two DataFrames, df1 and df2, and you want to merge them on the column id. You can do this by using the following code:

merged_df = pd.merge(df1, df2, on='id')

```
The merge function will return a new DataFrame that contains the merged data from both df1 and df2, based on the common values in the id column. This new DataFrame will contain all of the columns from both df1 and df2, so you may need to specify which columns you want to include in the final merged DataFrame using the columns keyword argument.

---

### Q11. How do you group data in a Pandas DataFrame by a specific column and apply an aggregation function?
A) Pandas **groupby** is used for grouping the data according to the categories and apply a function to the categories. It also helps to aggregate data efficiently.

---

### Q12. How do you pivot a Pandas DataFrame?
A) pandas.pivot(index, columns, values) function produces pivot table based on 3 columns of the DataFrame. Uses unique values from index / columns and fills with values.

---

### Q13. How do you change the data type of a column in a Pandas DataFrame?
A) **pandas.DataFrame.astype()** This method is used to assign a specific data type to a DataFrame column.

---

### Q14. How do you sort a Pandas DataFrame by a specific column?
A) Pandas **sort_values()** method sorts a data frame in Ascending or Descending order of passed Column.

---

### Q15. How do you create a copy of a Pandas DataFrame?
A) The **copy()** method returns a copy of the DataFrame.

```
import pandas as pd

data = {
  "name": ["Siri", "David", "John"],
  "age": [29, 30, 25]
}

df = pd.DataFrame(data)
print(df)

#Make a copy:

newdf = df.copy()

print(newdf)


output : 
    name  age
0   Siri   29
1  David   30
2   John   25

    name  age
0   Siri   29
1  David   30
2   John   25

```

---

### Q16. How do you filter rows of a Pandas DataFrame by multiple conditions?
A) Pandas DataaFrame can be filtered using **loc()** with multiple conditions.

---

### Q17. How do you calculate the mean of a column in a Pandas DataFrame?
A) DataFrame.mean() function is used to get the mean of a particular column from pandas DataFrame. 

```

import pandas as pd
technologies = {
    'Courses':["Spark","PySpark","Python","pandas",None],
    'Fee' :[20000,25000,22000,None,30000],
    'Duration':['30days','40days','35days','None','50days'],
    'Discount':[1000,2300,1200,2000,None]
              }
index_labels=['r1','r2','r3','r4','r5']
df = pd.DataFrame(technologies,index=index_labels)


# Using DataFrame.mean() method to get column average
df2 = df["Fee"].mean()
print(df2)


output :
24250.0

```
---

### Q18. How do you calculate the standard deviation of a column in a Pandas DataFrame?
A) By using **std()** function, we can calculate the standard deviation of a column in Pandas DataFrame. 

```
import pandas as pd

data = {
  "name": ["Siri", "David", "John"],
  "age": [29, 30, 25]
}

df = pd.DataFrame(data)
print(df)

output :

    name  age
0   Siri   29
1  David   30
2   John   25

print(df['age'].std())

output : 2.6457513110645907

```

---

### Q19. How do you calculate the correlation between two columns in a Pandas DataFrame?
A) Correlation is used to summarize the strength and direction of the linear association between two quantitative variables. It is denoted by r and values between -1 and +1. A positive value for r indicates a positive association, and a negative value for r indicates a negative association.

By using **corr()** function we can get the correlation between two columns in the dataframe.

```
# import pandas module
import pandas as pd

# create dataframe with 3 columns
data = pd.DataFrame({
	"column1": [12, 23, 45, 67],
	"column2": [67, 54, 32, 1],
	"column3": [34, 23, 56, 23]
}
)
# get correlation between element wise
print(data.corr())

output:

          column1   column2  column3
column1  1.000000 -0.997048  0.00000
column2 -0.997048  1.000000  0.07347
column3  0.000000  0.073470  1.00000

```

---

### Q20. How do you select specific columns in a DataFrame using their labels?
A) 

```
import pandas as pd

data = {
  "name": ["Siri", "David", "John"],
  "age": [29, 30, 25]
}

df = pd.DataFrame(data)
print(df)

output :
    name  age
0   Siri   29
1  David   30
2   John   25


print(df["age"])
output : 

0    29
1    30
2    25
Name: age, dtype: int64

```
---

Q21. How do you select specific rows in a DataFrame using their indexes?
A) Using  the **.iloc()** function we can select rows in a DataFrame using their indexes.

```
	name	age
0	Siri	29
1	David	30
2	John	25


df.iloc[0:1]

output :

    name	age
    
0	Siri	29

```

---

### Q22. How do you sort a DataFrame by a specific column?
A) Using **sort_values()** function we can sort specific column.

```
	name	age
0	Siri	29
1	David	30
2	John	25

df.sort_values(by=['age'])

output :

	name	age
2	John	25
0	Siri	29
1	David	30

```
---


### Q23. How do you create a new column in a DataFrame based on the values of another column?
A) Using **pandas.DataFrame.apply()** function we can create a new column ina DataFrame based on the values of another column.

```
	name	age
2	John	25
0	Siri	29
1	David	30

df['doubled_age'] = df.apply(lambda row : row.age*2, axis = 1 )

df

output :

	name	age	doubled_age
0	Siri	29	58
1	David	30	60
2	John	25	50

```
---

### Q24. How do you remove duplicates from a DataFrame?
A) Using **drop_duplicates()** method helps in removing duplicates from the DataFrame.

```
import pandas as pd
  
data = {
    "A": ["TeamA", "TeamB", "TeamB", "TeamC", "TeamA"],
    "B": [50, 40, 40, 30, 50],
    "C": [True, False, False, False, True]
}
  
df = pd.DataFrame(data)

df

output :
	A	B	C
0	TeamA	50	True
1	TeamB	40	False
2	TeamB	40	False
3	TeamC	30	False
4	TeamA	50	True


df_no_duplicates = df.drop_duplicates()

df_no_duplicates

output :


        A	B	C
0	TeamA	50	True
1	TeamB	40	False
3	TeamC	30	False

```
---


Q25. What is the difference between .loc and .iloc in Pandas?
A) **.loc** is to retrieve the data interms of rows and columns, it is a **label based data selecting method**. 

```
df.loc[rows, columns]
df.loc[3] "this retrieves the data in 3rd row".
df.loc[0:4, ["col_1", "col_2"]]
the above syntax retrieves rows from 0 to 4, specified columns.
``` 

**.iloc** is indexed based data retrieving method interms of rows and columns.
```
df.iloc[0:4, 1:5]
the above syntax retrieves rows from 0 to 4 and columns form 1st row to 4th row (5th row is excluded). 
```




