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
0	    Ankit	    21	    Math	    88
1	    Amit	    19	    Commerce	92
2	    Aishwarya	20	    Science	    95

```
---

### Q4. How do you rename columns in a Pandas DataFrame?
A) By using **rename()** method we can rename the columns in Pandas DataFrame.

```
print(df)

output:
	Duration	Pulse	Maxpulse	Calories
    -------------------------------------------
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

	DURATION	PULSE	Maxpulse	Calories
    ------------------------------------------
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
	Duration	Pulse	Maxpulse	Calories
    -------------------------------------------
0	60	        110	    130	        409.1
1	60	        117	    145	        479.0
2	60	        103	    135	        340.0
3	45	        109	    175	        282.4
4	45	        117	    148	        406.0

```

```
axis: int or string value, 0 ‘index’ for Rows and 1 ‘columns’ for Columns.
df.drop("Maxpulse", axis = 1)
print(df)

output:

	Duration	Pulse	Calories
    -----------------------------
0	60	        110	      409.1
1	60	        117	      479.0
2	60	        103	      340.0
3	45	        109	      282.4
4	45	        117	      406.0
```

---

Q6. How do you find the unique values in a column of a Pandas DataFrame?

Q7. How do you find the number of missing values in each column of a Pandas DataFrame?

Q8. How do you fill missing values in a Pandas DataFrame with a specific value?

Q9. How do you concatenate two Pandas DataFrames?

Q10. How do you merge two Pandas DataFrames on a specific column?

Q11. How do you group data in a Pandas DataFrame by a specific column and apply an aggregation function?

Q12. How do you pivot a Pandas DataFrame?

Q13. How do you change the data type of a column in a Pandas DataFrame?

Q14. How do you sort a Pandas DataFrame by a specific column?

Q15. How do you create a copy of a Pandas DataFrame?

Q16. How do you filter rows of a Pandas DataFrame by multiple conditions?

Q17. How do you calculate the mean of a column in a Pandas DataFrame?

Q18. How do you calculate the standard deviation of a column in a Pandas DataFrame?

Q19. How do you calculate the correlation between two columns in a Pandas DataFrame?

Q20. How do you select specific columns in a DataFrame using their labels?

Q21. How do you select specific rows in a DataFrame using their indexes?

Q22. How do you sort a DataFrame by a specific column?

Q23. How do you create a new column in a DataFrame based on the values of another column?

Q24. How do you remove duplicates from a DataFrame?

Q25. What is the difference between .loc and .iloc in Pandas?
