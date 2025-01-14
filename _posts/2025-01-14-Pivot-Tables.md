---
layout: post
title: Working with pivot tables		
date: 2025-01-14 20:00:00 +1000
categories: blogging, beginning, libraries, travel
---

## Pivot tables in pandas

Notes from datacamp lesson...I have found taking notes in a markdown file and creating as a post at the same time as the lesson has really helped with learning and recall.

*Subsetting and calculations with pivot tables*



how to call pivot tables:


```
df.pivot_table("column name containing numerical values to aggregate", index="columns to group by and display in rows", columns="columns to display as columns")
```
  
Pivot tables are dataframes with sorted indexes...

therefore can use loc and iloc on saved sorted dataframes…
  
e.g. 

```
df_sorted = df.pivot_table("value", index=, column=)
df_sorted.loc["rows", "columns"]
#slicing is particularly good for subsetting pivot tables
df_sorted.loc["row : row"]
  
```

methods for summary statistics...  
  
e.g. ```.mean()``` 
  
have an axis function ```df_sorted.mean(axis=)``` default value is "index" which calculates across rows (if axis isn't specified it will default to index).

Time to play with pivot tables apparently, 

Eddie(WTR) 


