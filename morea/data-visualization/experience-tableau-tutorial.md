---
title: "4. Tableau Tutorial"
published: true
morea_id: experience-tableau-tutorial
morea_type: experience
morea_summary: "Understand Tableau implementation basics"
morea_sort_order: 3
morea_labels:
  - 3:00pm
morea_enable_toc: true
---

# 4. Tableau Tutorial

<div class="alert alert-info mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* What is ParaView and how was it developed?
* How does the design of a user interface impact the ease and efficiency of creating visualizations?

**Objectives**
* Provide you with an understanding of the suitability of ParaView for your requirements.
* Demonstrate a series of simple steps for utilizing ParaView to generate a visual representation.
</div>

### Tableau: Revolutionizing Data Analysis and Visualization
<div style='text-align: justify;'>
In 2003, a group of computer science enthusiasts at Stanford embarked on a mission to make data analysis more accessible to everyone. The result was <a href="https://www.tableau.com/why-tableau/what-is-tableau">Tableau</a>, a data visualization software that has transformed the way people work with data. Chris Stolte, Pat Hanrahan, and Christian Chabot, the co-founders of Tableau, developed the software's groundbreaking technology, VizQL. VizQL is an intuitive interface that translates drag-and-drop actions into data queries, enabling users to visualize and analyze data seamlessly. With VizQL, users can quickly turn complex data sets into interactive, visual insights. Since its inception, Tableau has been committed to pushing the boundaries of data analysis and visualization. The company has invested heavily in research and development, resulting in innovative solutions that empower users to get answers faster and discover new insights. 

Today, Tableau is used by millions of people around the world, from individuals to large corporations, to make data-driven decisions. With its easy-to-use interface and powerful capabilities, Tableau continues to transform the way people work with data, making it more accessible and impactful than ever before. Tableau, which was acquired by Salesforce in 2019, is a company that is dedicated to enabling people to harness the power of their data. Their integrated analytics platform makes advanced technologies such as machine learning, statistics, natural language processing, and smart data prep more accessible to people, allowing them to augment human creativity with cutting-edge analytics tools.
</div>

### Initial Screen Overview
<div style='text-align: justify;'>
When you log into Tableau, you are presented with a dashboard-like interface. 
<br><br>
{% include figure.html url="" max-width="95%" file="/morea/data-visualization/fig/tab_initial.png" alt="tab" caption="" %}

The panel is divided into 3 sections. The left pane contains all the connectors, the middle pane contains the previous workbooks (marked with the number "3"), and the right pane contains resources to learn Tableau (marked with the number "4"). In the picture above, the section marked with the number "1" contains the file-connectors that allow you to load data from a file like .csv, .tsv or .hyper. The section marked as "2" is the Server connector that can be used to connect to a MySQL server or one from many other options it has. If your desired filetype is not in the file connectors list, you can click "More" to open a file browser. You will be able to select your desired file from there (marked with "*" in the following image).
<br><br>
{% include figure.html url="" max-width="95%" file="/morea/data-visualization/fig/tab_file_more.png" alt="tab" caption="" %}

Similarly, If your desired server connector is not in the server connectors list, you can click "More" to open a list of server connectors. At Tableau 2022.4.0 There were 73 available server connectors (Marked with "*" in the following image). It has popular data reservoirs like Google Bigquery (Marked with "1"), Google Drive (Marked with "2"), MySQL (Marked with "3"), Any Web data connectors (Marked with "4"). Even with this versatile range of options, if your desired connector can't be found in the list, you may create a custom connector for your datasource. 
<br><br>
{% include figure.html url="" max-width="95%" file="/morea/data-visualization/fig/tab_server_more.png" alt="tab" caption="" %}
</div>

### Load Datasoource
For this tutorial we shall use one of the most popular filetypes for storing data - .csv. Be aware, even we, most of the time, load .csv files with Excel, it's actually a text file where data is separated by a specific separator; most commonly the searator is a comma or tab. To load the data, we need to click 