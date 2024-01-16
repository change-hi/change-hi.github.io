---
title: "7. Applying GroupBy Operations"
published: true
morea_id: experience-advanced-operations-on-dataframes-2
morea_type: experience
morea_summary: "Understanding how to apply groupby operations"
morea_sort_order: 3
morea_labels:
  - 2:35pm
morea_enable_toc: true
---

# 7. Applying GroupBy Operations


##### 2.2.a) Aggregate

__Aggregations__ aggregate the data in each group, i.e., they reduce the data to a single value. This includes, for instance, computing group sums, means, maximums, minimums, _etc_. Some of the interesting/important summary aggregation methods of `GroupBy`  objects are:

|Methods| Decription|
|:----------|:----------------|
| `mean`, `median` | Computes the mean and the median in each group| 
| `min` , `max` | computes the min and max in each group| 
| `size` | computes the number of values in each group|
{: .table}

When one of these methods is called by the `GroupBy` object, it is applied to each group individually and then the group is combined into a new `DataFrame`.

For example, suppose we wanted to group `df` by `Region`, apply the `sum()` method to calculate the aggregate `Total Revenue` by `Region` and aggregate `Total Profit` by `Region`. Then we can combine the results into a new `DataFrame` which holds the aggregate `Total Revenue` by `Region` and the aggregate `Total Profit` by `Region`. We could achieve this by first splitting the data using the `groupby()` `DataFrame` method to obtain a new `GroupBy` object, we will call it `grouped_by_region`. Then we could apply and combine using the `GroupBy` object's `sum()` method.

<div class="alert alert-secondary" role="alert" markdown="1">
Code:
```python
grouped_by_region = df.loc[:, ['Region', 'Total Revenue', 'Total Profit']].groupby("Region")
grouped_by_region.sum()
```

Output:

|        | Total Revenue | Total Profit |
|--------|---------------|--------------|
| Region |               |              |
| Asia   | 6921531.31    | 2580972.04   |
| Australia and Oceania | 3292856.72 | 1236498.14 |
| Central America and the Caribbean | 6573837.78 | 1735667.38 |
| Europe | 1341328.03 | 347463.87 |
| Sub-Saharan Africa | 9980589.83 | 2990051.28 |
{: .table}
</div>

We see from the above example that the `GroupBy` `sum()` method returns a `DataFrame` with an index labeling the group that the row entry corresponds to and entries telling us the aggregate `Total Revenue` and aggregate `Total Profit` by `Region`.

##### Aggregate Continued

As discussed in the previous cell, `pandas` has implemented the most common aggregate methods for us, like `sum()` and `mean()`, but sometimes our data requires unique processing. The `GroupBy` method `agg()` can be used where complex or custom aggregation logic is required. The method `agg()` will take a function and use it to aggregate the group in the same way that we saw `sum()` do in the previous cell. The function passed must take a `DataFrame` as an argument, and that passed `DataFrame` will be each group of the calling `GroupBy` object.

For example, suppose we wanted to find the aggregate `Total Revenue` by Region in Canadian dollars. We can define a function called `sum_total_revenue_CAD()` to return the sum of the `Total Revenue` of a group in Canadian Dollars. Then we can create a new `GroupBy` object, call it `grouped_by_region`, using a subset of the `df` DataFrame only containing the `Region` and `Total Revenue` columns. Lastly, we can call `agg()` with the `grouped_by_region` GroupBy object and pass it the `sum_total_revenue_CAD` function.

<div class="alert alert-secondary" role="alert" markdown="1">
Code:
```python
def sum_total_revenue_CAD(x):
    return x.sum() * 1.33

grouped_by_region = df.loc[:, ["Region", "Total Revenue"]].groupby("Region")
grouped_by_region.agg(sum_total_revenue_CAD)
```

Output:

|        | Total Revenue |
|--------|---------------|
| **Region** |               |
| Asia                           | 9.205637e+06  |
| Australia and Oceania          | 4.379499e+06  |
| Central America and the Caribbean | 8.743204e+06 |
| Europe                         | 1.783966e+06  |
| Sub-Saharan Africa             | 1.327418e+07  |
{: .table}

</div>

We see in the above example that the result is a new `DataFrame` with the unique `Region` values as the index and values corresponding to the sum of the `Total Revenue` by `Region` in Canadian dollars.

To customize group-specific processing even further `agg()` can also take a dictionary of functions to aggregate on. The dictionary should be the name of a column of the group and the value of a callable function that will take a `Series`. 

For example, suppose we wanted to create a new `DataFrame` that tells us the sum of `Total Revenue` and the max `Total Profit` by Region from `df`. To do this we would first `groupby()` `Region` and then call `agg()` with the new `GroupBy` object, passing it the dictionary: `{'Total Revenue' :sum,'Total Profit' : max}`, which specifies that we want to sum the `Total Revenue` column and find the max of the `Total Profit` column.

<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
grouped_by_region = df.groupby("Region")
grouped_by_region.agg({'Total Revenue' :sum,'Total Profit' : max})
```

Output:

|        | Total Revenue | Total Profit |
|--------|---------------|--------------|
| **Region** |               |              |
| Asia                           | 6921531.31    | 1208744.24   |
| Australia and Oceania          | 3292856.72    | 951410.50    |
| Central America and the Caribbean | 6573837.78 | 1487261.02   |
| Europe                         | 1341328.03    | 224598.75    |
| Sub-Saharan Africa             | 9980589.83    | 693911.51    |
{: .table}
</div>

##### 2.2.b) Transform

 __Transformations__ change the data in a group-specific way. As opposed to aggregations, which reduce the data into a single value, transformations modify the data but don't change the shape of the groups.

Applying a transformation is done using the `transform()` `GroupBy` method. The `transform()` method takes as input a function name, which it calls on each group of the `GroupBy` object. The function passed to `transform()` must take a `DataFrame`, which will be a group of the calling `GroupBy` object. 

For example, suppose we wanted to transform the `Total Revenue` column of the `df` DataFrame to hold the percentage of the Total Revenue by Region that rows make up.  First, we would define a function that will take a `DataFrame` and calculate the percentage of the total each entry takes up. Then we will create a new `GroupBy` object grouped by `specialty` from a subset of `df` that only has the columns `Total Revenue` and `Region`. Then we will call transform passing it the name of our defined function. 

<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
def my_function(x):
    return (x   / x.sum() ) * 100
grouped_by_region = df.loc[:, ["Region", "Total Revenue"]].groupby("Region")
grouped_by_region.transform(my_function)
```

Output:

|    | Total Revenue |
|----|---------------|
| 0  | 76.943949     |
| 1  | 8.773913      |
| 2  | 86.369819     |
| 3  | 0.757387      |
| 4  | 33.028359     |
| 5  | 23.056051     |
| 6  | 28.034881     |
| 7  | 12.475344     |
| 8  | 4.970659      |
| 9  | 13.588176     |
| 10 | 0.276000      |
| 11 | 4.563649      |
| 12 | 13.045966     |
| 13 | 91.226087     |
| 14 | 5.787140      |
| 15 | 13.630181     |
| 16 | 43.912456     |
| 17 | 2.581546      |
| 18 | 36.978437     |
{: .table}
</div>

We see that the result is a new `DataFrame` with an index matching that of the original `DataFrame` used to initialize the `GroupBy` object. This is different than the aggregation example because aggregation reduces the group to a single value, while transformation maintains the shape of the calling `DataFrame`.

Let us save these results into a new column in `df` called `Total_Revenue_Percentage`.

<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
df["Total_Revenue_Percentage"] = grouped_by_region.transform(my_function)
```
</div>

Suppose we wanted to see the percent Total Revenue by `Order Priority` and `Region`. One solution to achieve this would be to group on both the `Region` and the `Order Priority` columns and then sum the `Total_Revenue_Percentage` that was computed previously.

<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
order_priority_pct = df.loc[:, ["Region", "Order Priority", "Total_Revenue_Percentage"]].groupby(["Region", "Order Priority"]).sum()
order_priority_pct.head(n=4)
```

Output:

|        |                | Total_Revenue_Percentage |
| Region | Order Priority |                          |
|--------|----------------|--------------------------|
| Asia   | C              | 5.787140                 |
|        | H              | 0.276000                 |
|        | L              | 50.024403                |
|        | M              | 43.912456                |
{: .table}
</div>

Notice that since we are grouping on two columns, the resulting index of `order_priority_pct` also contains two columns. Now we can sort first on the values in the `Region` column so that all the entries with a common `Region` are clustered together, and then on the values in the `Total_Revenue_Percentage` columns.

<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
order_priority_pct = df.loc[:, ["Region", "Order Priority", "Total_Revenue_Percentage"]].groupby(["Region", "Order Priority"]).sum()
order_priority_pct.sort_values(["Region", "Total_Revenue_Percentage"], ascending=[True, False]).head(n=6)
```

Output:

|                       |                | Total_Revenue_Percentage |
| Region                | Order Priority |                          |
|---------------------- |----------------|--------------------------|
| Asia                  | L              | 50.024403                |
|                       | M              | 43.912456                |
|                       | C              | 5.787140                 |
|                       | H              | 0.276000                 |
| Australia and Oceania | H              | 76.943949                |
|                       | C              | 23.056051                |
{: .table}
</div>

##### 2.2.c) Filter

 __Filtering__  a group consists of dropping or retaining groups in a way that depends on a group-specific computation that returns `True` or `False`. Groups that are retained will be left unmodified. For instance, we can filter specialties from `spending_df` that don't have enough entries or for which the mean `spending` is below a certain threshold.

Filtering a group is done using the `GroupBy` method `filter()`. The method `filter()` takes as input a function name, which it calls on each group of the `GroupBy` object. The function must return either `True` or `False` and groups for which the function returns `False` are dropped. The resulting `DataFrame` will have entries in the same order as the original `DataFrame`.


Suppose we want to filter out the **Regions** that having low Total Revenue, i.e. we want to filter out the Regions for which the aggregate `Total Revenue` is less than some defined threshold, let say $4,000,000. To do this we can define a function named `filter_on_total_revenue()`. The defined function will take a `DataFrame`, determine whether the sum of the `Total Revenue` column in that `DataFrame` is less than 5000000, and then return `True` if it is or `False` if not. 

Then, to apply the filter on `df`, we first subset the `DataFrame` so that only the columns `Region` and `Total Revenue` are remaining and then group by `Region`. Then the `GroupBy filter()` method can be called with the `filter_on_total_revenue()` function passed as an argument. We can save the results into a new `DataFrame` named `low_revenue_df`. Then to see which Regions are less than the $4,000,000 Total Revenue threshold we can print the unique values in the `Region` column of `low_revenue_df`.


<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
def filter_on_total_revenue(x):
    return x['Total Revenue'].sum() < 4000000
low_revenue_df = df[["Region", "Total Revenue"]].groupby("Region").filter(filter_on_total_revenue)
low_revenue_df["Region"].unique()
```

Output:
```python
array(['Australia and Oceania', 'Europe'], dtype=object)
```
</div>

We see that only two Regions are under the threshold of Total Revenue.

###### Thinning Data and The Flexible `apply()`  GroupBy Method

`pandas` provides a few built-in `GroupBy` methods for thinning the data including `nlargest()`, `nsmallest()`, and more. An example usage of `nlargest()`, a thinning method, would be grouping a subset of `df` which contains only the `Total Revenue` and `Region` columns by `Region` and then obtaining the 2 largest of each Region. The result will be a new `DataFrame` with only the top 2 spenders from each unique specialty.


<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
grouped_by_region = df.loc[:, ["Region", "Total Revenue"]].groupby("Region")
grouped_by_region["Total Revenue"].nlargest(2).head(n=4)
```

Output:
```python
Region                   
Asia                   16    3039414.40
                       18    2559474.10
Australia and Oceania  0     2533654.00
                       5      759202.72
Name: Total Revenue, dtype: float64
```
</div>
    
Though `pandas` has the more common and basic aggregation, transformation, and thinning methods implemented for us, they could not possibly cover all cases. Therefore cases that do not fit into any one of these categories may be carried out by using the more flexible `apply() GroupBy` method. `apply()` takes as input a function name, which it calls on each group of the calling `GroupBy` object.

For example, suppose we wanted to thin our dataset so that there are only 50% of each specialty represented. To do this we can define a new function, we will call it, `sample_50p`, and this function will utilize the `sample()` `DataFrame` method. The `sample()` `DataFrame` method will take a parameter `frac` that specifies the fraction of the original `DataFrame` that is to be returned. We can then use the `apply()` method and pass it the name of our newly defined function to obtain a new `DataFrame` that is filtered at the group-specific level. 

<div class="alert alert-secondary" role="alert" markdown="1">

Code:
```python
def sample_50p(x):
    return x.sample(frac=0.5)
grouped_by_region = df.loc[:, ["Region", "Total Revenue", "Order Priority"]].groupby("Region")
grouped_by_region.apply(sample_50p).head(n=5)
```

Output:

|                              |       | Region                   | Total Revenue | Order Priority |
| Region                       |       |                          |               |                |
|------------------------------|-------|--------------------------|---------------|----------------|
| Asia                         | 10    | Asia                     | 19103.44      | H              |
|                              | 18    | Asia                     | 2559474.10    | L              |
| Australia and Oceania        | 0     | Australia and Oceania    | 2533654.00    | H              |
| Central America and the Caribbean | 1 | Central America and the Caribbean | 576782.80 | C              |
| Europe                       | 15    | Europe                   | 182825.44     | M              |
{: .table}
</div>












<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
**Function Application and Mapping**

* **Global Processing**
  * To apply a function to every row or column in a `DataFrame` we can use the `apply()` method
  * To apply a function to every element in a `Series` we can use the `map()` method
  * To apply a function to every element in a `DataFrame` we can use the `applymap()` method
  
* **Group Specific Processing**

  * The `groupby()` method is used to group the data using values on one or more columns

  * `groupby()` is often applied in the context of the data processing paradigm called "split-apply-combine"
    * **Split**: you need to split the data into chunks defined using one or more columns
    * **Apply**: apply some operation on the chunks generated. 
    * **Combine**: combine the results of the applied operation into a new `DataFrame`

  * There are 3 common classes of split-apply-combine operations that can be applied to group data.

    1. __Aggregations__ generate a single value for each group
  
    2.  __Transformations__ convert the data and generate a group of the same size as the original group.

    3.  __Filters__ retain or discard a group based on group-specific boolean computations.
</div>



<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>
You can read more about `groupby` from the official pandas documentation of [groupby](https://pandas.pydata.org/docs/user_guide/groupby.html)
</div>


{% include next-button.html
top-label="7. Real Example Cleanup>"
bottom-label="3:05pm"
url="/morea/data-wrangling-2/experience-real-example-cleanup.html" %}

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Bio Break!**
We will start again at 3:05 PM.
<hr/>
</div>