---
layout: post
title: Slicing and subsetting with .loc and .iloc		
date: 2025-01-11 11:10:00 +1000
categories: blogging, beginning, libraries, travel
---


# slicing and subsetting with pandas


#### **Lecture Notes**

#### Slicing a list:  

```list[1st position you want, last element (not included in output)]```

omitting will start at the beginning... ```[ :3]``` for example

if you inputted ```[:]``` you would get the whole list. 

## Slicing a DF

**When slicing dataframes you need to sort the index first:**  
  
```variable name = df.set_index([column, column]).sort_index()```




### **.loc**

#### Basic Syntax: 

```df.loc[rows, columns]```  

this would do a multilevel index by giving a range of rows:  
```df.loc["row name 1" : "Last row you want"]``` this time the last value ***is*** included. This method only works on the outer index level. 

To slice it into an inner index you have to pass the row names as tuples...

```
df.loc[("outer index element to start with", "inner index level to start with"):("outer index element to finish with, inner index level to finish with)]
```

for slicing columns...

```df.loc[:, "column to start with":"column to finish with"]```  


combine these for slicing rows AND columns.  
  
If you are doing dates as the rows to be sliced...just including the year will give you all values for that year. e.g. ```df.loc["2023":"2024"]``` gives all values for 2023 and 2024.  


### **.iloc**

.iloc function slices based on integer position of the rows and columns. In this case the final values AREN'T included in the slice (just like lists). 

Time to Practice! 

Eddie (WTR)









