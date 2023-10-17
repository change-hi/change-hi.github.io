---
title: "2. Google Colab Interface"
published: true
morea_id: experience-jupyter-interface
morea_type: experience
morea_summary: "Understand how the google colab interfrace is setup"
morea_sort_order: 3
morea_labels:
  - 2:10pm
morea_enable_toc: true
---

# 2. Google Colab Interface

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* Describe the basics of the Google colab interface.
* Demonstrate the various basic cell types notebooks use.
* Demonstrate how notebooks deal with code blocks and the concept of restarting the runtime.

</div>

## Notebook Basics

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

The button above will take you to Google Colab where you can start a new notebook or open an existing one. When you load up the Colab page, you should be presented with a site that looks something like the image below.

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/Colab Int.JPG" alt="Basic Binder Webpage" caption="" %}

If, after clicking the button, you encounter the message **"We are sorry, but you do not have access to this serive. Please contact your Organization Administrator for access."** please follow the instructions provided in this [link](https://www.hawaii.edu/askus/1649) to enable consumer apps.

Colab site contains a variety of buttons. However, for now we are going to do the following:

Click on the **New Notebook**. This will create a colab notebook called `Untitled0.ipynb` with a single blank cell. You will be presented with a new screen which will look something like the image below.

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/untitled0.PNG" alt="New Notebook Page" caption="" %}

This notebook is blank except for a single cell. This blank cell is a code cell that you can type in. For example if you type in some python code like `print("This is a code cell")` and then click the run button you will see the output appear beneath the cell.

### Cell Types

Cells are the base unit in Google notebooks. A notebook is essentially just a collection of cells of different types. In Google notebooks there are two primary types of cells:

- **Code** cells
  - Code cells treat everything typed inside them as code
  - When they are **run** they will run the code they find inside them
- **Markdown** cells
  - Markdown cells treat everything typed inside them as markdown
  - When they are **run** they format the text based on standard markdown conventions, allowing for stylized text, links, lists, and more

If you check this file called [Notebook-interface.ipynb](https://colab.research.google.com/github/mahdi-b/change-hi.github.io/blob/main/morea/data-wrangling-1/Notebook/02-jupyter-notebook-interface.ipynb), you will be presented with a notebook that already has some cells filled in. Underneath the header **Cell Types** you will find two different cells that each correspond to one type of cell. You can select the top cell and then click the run button to run all the cells.

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

Markdown cell can be edited and run repeatedly without much issue. However, when editing code blocks you have to be more careful. When you run a code cell you are running that piece of code. Even if you delete or edit the code block after running it the changes it made will remain until the Runtime is restarted.

A good way to think about code cell execution in a notebook is that you are essentially copy pasting the code cell into a python console. The image below gives a visual example of this with the notebook cells on the left, and a python code that does the same set of commands on the right. You can try running the cells found in the left image by looking for the header **Editing Cells** in this file [Notebook-interface.ipynb](https://colab.research.google.com/github/mahdi-b/change-hi.github.io/blob/main/morea/data-wrangling-1/Notebook/02-jupyter-notebook-interface.ipynb).

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/E2_4_running_code.png" alt="Running Code" caption="" %}


To show the dangers of rerunning cells we can try rerunning the two bottom cells containing the code `a = a + 2` and `print(a)`. This will be reflected as a fifth and sixth command executed in the python console. You can see this reflected in the Python console below where the same commands have been issued in the same order. So despite the fact that we only have four cells of python we have executed 6 cells worth of code.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Re-running Cells**
<hr/>

Rerunning code cells will erase the output of that code cell and update the counter next to the cell with the most recent time the cell was run.

</div>

{% include figure.html url="" max-width="60%" file="/morea/data-wrangling-1/fig/E2_5_rerunning_code.png" alt="Rerunnig Cells" caption="" %}


Rerunning code cells is **not recommended** since it obscures what the notebook's code cells are doing and can make it very difficult for anyone reading your notebook to accurately rerun your analysis.


<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
* A notebook is divided into cells that are either code or markdown.
* Cells can be \"run\" leading to either the execution of code or formatting of markdown depending on the cell type.
* Code cells can be rerun, but this should be avoided to prevent obscuring the notebooks workflow.
</div>



{% include next-button.html 
           top-label="3. Loading and Handling Pandas Data ->" 
           bottom-label="2:20pm" 
           url="/morea/data-wrangling-1/experience-data-structures.html" %}
