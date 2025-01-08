---
layout: post
title: Manipulating data in pandas (revision)
date:   2025-01-09 09:43:00 +1000
categories: blogging, beginning
---

# **Datacamp lesson - Slicing and subsetting with .loc and .iloc**

Still learining Markdown...but here goes. 

Going through datacamp and learning python...sometimes I think i'm starting to get it...and sometimes I don't.  

For some reason slicing and indexing lists and dataframes has a hard time sticking in my brain...

.loc - calling locations within a pandas library...selects rows and columns by labels or a boolean array...
	can use when you know the index labels or column names

.iloc - selects rows and columns by integer positions. 

I've done this before in the intermediate python track on datacamp, but going back over it to really make it stick, in doing so I sorted out more about how to think about programming, stepping through what I am trying to tell the program to do, and I think I understand subsetting a dataframe a little better. 

Plan for tonight is to go over the datacamp revision exercises for the last few days...
 
  
## Transorming DataFrames   

**.sort_value()**  
sorts values of a dataframe, can use subsetting..


## Data Manipulation

Practice sessions through datacamp...  

### **?How to figure out the proportion of a particular column within a dataframe?**  

-> subset the column using df["column"]  
-> call the .value_counts() method  
-> the normalise argument for the value counts method divides each count by the total number of elements in the series (column), gives these as a decimal  
-> without normalise = True, will return the absolute counts of each unique variable within the series (column)  

*for example:*
{
print(sales["product_line"].value_counts(normalise = True))
} 
  
In a dataframe names 'sales', this would work out the proportion of each product line within the entire dataset. 


And finally just finished this post this morning with Halle's help, datacamp has a great revision feature and Halle can input the answers to questions for me using numbers and the enter key. 


Lets see how this looks...

Eddie(WTR)  












**Grouped summary statistics and pivot tables**

**
