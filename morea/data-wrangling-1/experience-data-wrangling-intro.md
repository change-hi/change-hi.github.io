---
title: "1. Data Wrangling Introduction"
published: true
morea_id: experience-data-wrangling-intro
morea_type: experience
morea_summary: "Understand why Jupyter notebooks are useful for data wrangling"
morea_sort_order: 2
morea_labels:
  - 2:00pm
morea_enable_toc: true
---

# 1. Data Wrangling Introduction

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
  * What are the essential steps in data wrangling?
  * Why are Jupyter notebooks useful for cleaning and wrangling data?

**Objectives**
  * Understand how data wrangling utilized in data science.
  * Understand how Jupyter notebooks provide a method of documenting the steps involved in cleaning and wrangling data.

</div>

### What should we care about data wrangling?

Data scientists devote the bulk of their time to the routine work of collecting and preparing messy digital data, prior to it being analyzed for valuable gems. While new libraries have emerged to assist with data handling, the data itself has grown more complex and voluminous, thereby maintaining pace with the ongoing challenges in data science.


If you've ever worked with data in Excel, Google Sheets, or a CSV file, you've likely needed to tweak it somehow before it's useful. Maybe you've added or removed columns and rows, or carried out summations or other arithmetic functions. These tools work great for simple tasks. But what happens when you need to apply more complex functions or operations? The standard tools fall short as they lack more sophisticated functions, and reusing existing libraries becomes a challenge, as they're primarily not designed for such platforms or scenarios. Similarly, repeating the same steps to multiple datasets is neither scalable nor reproducible.

Addressing these limitations, Python stands out as a powerful language that can handle most intricacies of working with data. Notably, the Pandas library is recognized as the quintessential standard in data processing, providing powerful tools for managing substantial datasets, executing complex functions, and creating reusable scripts. Its proficiency far surpasses the elementary functionalities of conventional tools like Excel or Google Sheets.

While there are many tools available for coding and data wrangling, Jupyter Notebooks have become the go-to option for these tasks. Jupyter Notebooks are an open-source web-based application that allows you to create and share documents containing code, equations, visualizations, and narrative text. Their popularity stems from their interactive nature, allowing you to write brief code snippets, examine the results, and iterate as needed. Jupyter notebooks also allow users to mix code, visuals, and text in one place. This setup makes writing workflow easy to follow and document, which is ideal for collaboration and for dissemination. Furthermore, Jupyter supports multiple languages and connects well with data science tools, making it a versatile choice for different projects. 

In this first workshop, you will learn the basics of utilizing jupyter notebooks by using Pandas ([Link to Pandas Website](https://pandas.pydata.org/)) and the Jupyter environment. The Pandas library helps provide various bells and whistles for both cleaning and analyzing your data. However, since it is built on top of Python a basic understanding of the Python ([Link to Python Website](https://www.python.org/)) programming language is required. Through these tools you will learn how to analyze a raw dataset by cleaning it up and formatting it so that it can be used for further analysis or other workflows.

### What this lesson will **not** teach you

- How to write basic python code
- How to set up a notebook environment on your machine
- How to run other programming languages e.g. R in jupyter notebooks

> ## Notebook Programming Languages
>
> Jupyter notebooks can contain various programming languages with R or Julia being possibilities.
>
{: .callout}

### Lesson Structure

The structure for this lesson will require participants to run a jupyter notebook. In order to reduce the time required to get Jupyter notebooks setup and running we will be utilizing [Google Colab](https://colab.research.google.com/)), an  online Jupyter Notebooks environment from Google. At the beginning of each module, you'll find a link directing you to the Colab notebook website specific to that lesson.


<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
* Pandas is a software library used primarily for data manipulation and analysis. It offers data structures and operations for manipulating numerical tables and time series using Python.
* Jupyter Notebooks are an open-source web application that allows you to create and share documents containing live code, equations, visualizations, and narrative text. They're widely used for data analysis, scientific research, and education.
</div>


<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Acknowledgements**
<hr/>

This workshop contains material we used and modified from the [Introduction to Data Wrangling with Computational Notebooks workshop](https://ci-tracs.github.io/Data_Wrangling_with_Computational_Notebooks/).

</div>

{% include next-button.html 
           top-label="2. Google Colab Interface ->" 
           bottom-label="2:10pm" 
           url="/morea/data-wrangling-1/experience-jupyter-interface.html" %}
