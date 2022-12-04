# Introduction to Statistic in Python

## What is Statistics?
- **The field of statistic:** It is the practice and study of collecting and analyzing of data.
- **A summary statistics:** a fact about the summary of data e.g.(average or count).


## What statistic can do?
- How likely is someone to purchase a product?
- Are people more likely to purchase it if they can use a different payment system? 
- How many occupants will your hotel have? How can you optimize occupancy?
- How many sizes of jeans need to be manufactured so they can fit 95% of the population? Should the same number of each size be produced?
- A/B test: which ad is more effective in getting people to purchase the product?

## What can't statistics cant do?
While statistics can answer a lot of questions, it's important to note that statistics can't answer every question, because they may lie or leave out reasons.

**example**:
- why the TV series Game of Thrones is so popular?

**instead...**
- are series with more violent scenes viewed by more people?

**But...**
- even so, this can't tell us if more violent scenes lead to more views

## Types of statistics

**Descriptive statistics**
  - Describe and sumarize data at hand
  **example:**
  * ask four friends how they get to work
    - 50% of friends commute
    - 25% drive to work
    - 25% bike
  
**Inferential statistics**
  - use sample data to make inferences about a larger population
  **example:**
  What percentage of people drive at work?


## Types of data
**Note**: this aren't the only type of data that exists.

**Numeric (Quantitative)**
this are made up of numeric values
  - Continuous (Measured)
    - car speed
    - time spent on line

  - Descrete (counted)
    - number of pets
    - number package shiped

**Categorical (Qualitative)**
this are made up of values that belongs to distinct groups
  - **Nominal(Unordered)**
    - Married/Unmarried(1/0)
    - Country residence(1,2...)

  - **Ordinal (Ordered)**
    - likert scale 

**note:** Categorical data can be represented as numbers

## Why does data type matter?
Identifying the type of data your working is important since it will dictate the type of summary statistics or visualization that makes sense to the data

**example:**
- **Numeric data**
  - **Summary statistics:**
      get the mean:
      ```python
      import numpy as np
      np.mean(car_speeds['spped_mph'])
      ```
  - **Plots:**
    - Scatter plot
    - hist

- **Categorical data**
  - **Summary statistics:**
      get counts of unique value:
      ```python
      demographic['marriage_status'].value_counts()
      ```
  - **Plots:**
    - bar plot
