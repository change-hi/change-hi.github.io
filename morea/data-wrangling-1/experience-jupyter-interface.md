---
title: "2. Google Colab Interface"
published: true
morea_id: experience-jupyter-interface
morea_type: experience
morea_summary: "Understand how the google colab interfrace is setup"
morea_sort_order: 3
morea_labels:
  - 2:20pm
morea_enable_toc: true
---

# 2. Google Colab Interface

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mahdi-b/change-hi.github.io/blob/main/morea/data-wrangling-1/Notebook/02-jupyter-notebook-interface.ipynb)

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Objectives**
* Provide an overview of the fundamental features of the Google Colab environment.
* Illustrate the different cell categories utilized in Notebook environments.
* Show how notebooks handle segments of code and explain the idea of rebooting the runtime.
</div>

## Notebook Basics

Clicking the [following URL](https://colab.research.google.com/) will take you to Google Colab where you can start a new notebook or open an existing one. When you load up the Colab page, you should be presented with a layout that closely resembles that in the image below.

{% include figure.html url="" max-width="80%" file="/morea/data-wrangling-1/fig/Colab Int.JPG" alt="Basic Binder Webpage" caption="" %}

If, after clicking the button, you encounter the message **"We are sorry, but you do not have access to this serive. Please contact your Organization Administrator for access."** please follow the instructions provided in this [link](https://www.hawaii.edu/askus/1649) to enable consumer apps.

With the Open notebook modal window open, click on the **New Notebook**. This will create a colab notebook named `Untitled0.ipynb`, containing  a single blank cell. Your view of the web page should appear similar to the image shown below. A cell in a Jupyter Notebook is essentially a single editable unit that acts as a container for either code or text. Imagine it as a piece of digital paper where you can write a script or make notes. 

{% include figure.html url="" max-width="80%" file="/morea/data-wrangling-1/fig/untitled0.PNG" alt="New Notebook Page" caption="" %}

As you'll notice the notebook contains a single cell, which is still empty. Type

`print("290 + 180 = ", 290 + 180)`

and then click the run button (triangle at the right side of the cell) you will see the output appear below the cell.

### Cell Types

Cells are the base unit in Google notebooks. A notebook is essentially just a collection of cells of different types. In Google notebooks there are two primary types of cells:

- **Code** cells
  - Code cells treat everything typed inside them as code (Python by default)
  - Code can be executed -- we often say running the cell --  by clicking the **run** button on the immediate left of  the cell.
- **Markdown** cells
  - Markdown cells treat everything typed inside them as markdown, an easy to read and write formatting syntax, to format text, links, lists, and more.
  - When they are **run**, jupyter formats the text they contain and diplays it below the cell.  

If you click Open in Colab button at the top of this page, you will be presented with a notebook that already has some cells filled in. Underneath the header **Cell Types** you will find two different cells that each correspond to one type of cell. You can select the top cell and then click the run button to run all the cells.

If you wish to rename the file, click on `Notebook-interface.ipynb` in the top-left corner. You can then enter a new name for the file. Refer to the image below for guidance.

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/filename.PNG" alt="New Notebook Page" caption="" %}

> ## Running Cells
>
> You can also run a selected cell by pressing <kbd>Shift</kbd>+<kbd>Return</kbd>
>
{: .callout}

You will see that the action performed after running a cell is different for each of the cells.

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/Cell.PNG" alt="Notebook Cell Types" caption="" %}


### Editing Cells

You can also edit cells after running them by clicking on the cell like normal text. For markdown cells you will need to double click on the cell area in order revert it back into a editable format.

When modifying code cells, caution is required as any changes — including deletions or edits made to the cell afterward — won't alter the effects the previous run of the cell had. These effects persist until the cell is rerun with new values of the runtime or runtime is restarted.


The image below gives a visual example of this with the notebook cells on the left, and a python code that does the same set of commands on the right. You can try running the cells found in the left image by looking for the header **Editing Cells** in this Notebook referenced from the Open in Colab button above.

{% include figure.html url="" max-width="80%" file="/morea/data-wrangling-1/fig/E2_4_running_code.png" alt="Running Code" caption="" %}


To show the dangers of rerunning cells we can try rerunning the two bottom cells containing the code `a = a + 2` and `print(a)`. This will be reflected as a fifth and sixth command executed in the python console. You can see this reflected in the Python console below where the same commands have been issued in the same order. So despite the fact that we only have four cells of python we have executed 6 cells worth of code.

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/E2_5_rerunning_code.png" alt="Rerunnig Cells" caption="" %}

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Re-running Cells**
<hr/>

Rerunning code cells will erase the output of that code cell and update the counter next to the cell with the most recent time the cell was run.
</div>

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
* A notebook is divided into cells that are of type code or markdown.
* Markdown cells enhance documentation by allowing users to insert images, videos, equations, and apply text styling, enhancing the notebook's readability and comprehensiveness.
* Jupyter facilitates an interactive coding environment, enabling users to write and execute code in real-time, view the results immediately, and make iterative improvements, promoting a more efficient and explorative workflow.
</div>



{% include next-button.html 
           top-label="3. Loading and Handling Pandas Data ->" 
           bottom-label="2:20pm" 
           url="/morea/data-wrangling-1/experience-data-structures.html" %}
