---
title: "6. Advanced Operations on Series and DataFrames"
published: true
morea_id: experience-advanced-operations-on-dataframes
morea_type: experience
morea_summary: "Understanding advanced functions that can be applied on Series and DataFrames like groupby"
morea_sort_order: 3
morea_labels:
  - 2:10pm
morea_enable_toc: true
---

# 6. Advanced Operations on Series and DataFrames

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How do you create data chunks using values on one or more columns?
* How do you apply some operation on created data chunks?
* How do you combined the results (processed chunks) into a new `DataFrame` ?

**Objectives**
* Learn how to group data based on a column/s using `groupby`.
* Learn how to process created data groups.
* Learn how to combine the results together.

</div>

## Global Processing Vs. Group Specific Processing

Function application falls into one of two categories:

1. **Global Processing**
2. **Group Specific Processing**

Global processing is applying the same function to every entry (referring to a singular data point or an entire row or column) in a `Series` or `DataFrame`. Group specific processing, on the other hand, is applying functions to entries that belong to a certain group based on some defining characteristic.

We will begin by covering global processing in the following cells.

### Global Processing

In one clever way or another, every global processing problem you will ever run into when working with `DataFrames` will fit into one of two levels of granularity. Corresponding to these two levels are two `DataFrame` methods, `apply()` and `applymap()`.

To apply a function to every row or column of a `DataFrame` we use the `apply()` `DataFrame` method. The `apply()` method takes a function that will be applied to the specified axis (columns or rows), the axis, and other keyword arguments that are defined by default. Depending on the function passed to the `apply()` can behave in the same way as the `applymap()` function.

#### Global Processing-apply()
Let us look at two examples use cases, using a reducing function, and a universal function. The function passed to the `apply()` method will process a `Series`, either a `DataFrame` row or column depending on the axis parameter, and return a result. 

Most of the time when you call the `apply()` method you should be using a reducing function. A reducing function is one which takes a `Series` object and reduces the `Series` to a either a new `Series` or a single entry using a process that relies on data in the `Series`. You are already familiar with some reducing functions such as the `Series` `sum()` method, which returns the sum of all the entries in the calling `Series`. Consider the following example of calling `apply()` with a reducing function.

```python
>>> df = pd.DataFrame([[ 0,  3,  6], [ 9, 12, 15], [18, 21, 24]], columns=['a', 'b', 'c'])
>>> def square_sum(x_series):
>>>    return x_series.sum() ** 2
>>> df.apply(square_sum, axis=1) # apply to each row
0      81
1    1296
2    3969
dtype: int64
```

The reducing function, `square_sum()` in the example above sums all the entries in the `Series` and the squares the result. You can define custom reducing functions just like we showed above to to achieve your desired analysis.

A universal function will return a new `Series` that was created by universally applying the same procedure to each `Series` entry. A universal function can be defined using the `Series` `map()` method. The `map()` method will take a function as an argument which will process each individual `Series` entry according to the function definition. For instance refer to the following code example.

```python
>>> df = pd.DataFrame([[ 0,  3,  6], [ 9, 12, 15], [18, 21, 24]], columns=['a', 'b', 'c'])
>>> def divide_by_three(x_series):
>>>    return x_series.map(lambda x: x / 3)
>>> df.apply(divide_by_three, axis=0) # apply to each column
     a    b    c
0  0.0  1.0  2.0
1  3.0  4.0  5.0
2  6.0  7.0  8.0
```

The example above shows how the `apply()` method behaves when a universal function is passed as the argument. The resulting `DataFrame` is constructed from original `DataFrame` except each individual entry is divided by three.

#### Global Processing-applymap()
There is a shorthand way achieve the same exact behavior shown in the example of applying a universal function in the **Global Processing-apply()** cell above, and the method is appropriately named `applymap()`, as first we call the `apply()` `DataFrame` method and then we call the `map()` method. 

To apply a function to every individual element in a `DataFrame` we can use the `applymap()` `DataFrame` method.  The `applymap()` method is a function which takes one positional argument as input and that is a callable function which takes a single value and returns a single value. The `applymap()` method will apply the function passed to every single entry in the calling `DataFrame` and return a new `DataFrame` with the processed entries.

Let us see a simple example. We will construct a `DataFrame` `df` that is $3 \\times 3$, i.e. there are three rows and three columns. The entries will be consecutive multiples of 3. To each entry we will apply the anonymous function: `lambda x: x / 3` which will divide a given input by 3. The result will be a new $3 \\times 3$ `DataFrame` with the same index and columns as the caller with entries that are the results of the passed function.

```python
>>> df = pd.DataFrame([[ 0,  3,  6], [ 9, 12, 15], [18, 21, 24]], columns=['a', 'b', 'c'])
>>> df.applymap(lambda x: x / 3)
     a    b    c
0  0.0  1.0  2.0
1  3.0  4.0  5.0
2  6.0  7.0  8.0
```

This type of processing is relatively rare since it should be the case that it makes sense to apply the same function to every entry regardless of its location. For example, in the `spending_df` `DataFrame` there are few functions that would be reasonable to apply globally. But when you need this functionality, the `applymap()` function is quite useful. 

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>

</div>


{% include next-button.html
top-label="7. Real Example Cleanup>"
bottom-label="3:50pm"
url="/morea/data-wrangling-2/experience-real-example-cleanup.html" %}