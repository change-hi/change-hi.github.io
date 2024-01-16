---
title: "2. Introducing the Shell"
published: true
morea_id: experience-ssb-intro
morea_type: experience
morea_summary: "What is a command shell and why would I use one?"
morea_sort_order: 4
morea_labels:
  - 2:10pm
morea_enable_toc: true
---

# 2. Introducing the Shell

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Key Points**
  * A shell is a program whose primary purpose is to read commands and run other programs.
  * This lesson uses Bash, the default shell in many implementations of Unix.
  * Programs can be run in Bash by entering commands at the command-line prompt.
  * The shell's main advantages are its high action-to-keystroke ratio, its support for automating repetitive tasks, and its capacity to access networked machines.
  * The shell's main disadvantages are its primarily textual nature and how cryptic its commands and operation can be.

**Objectives**
  * Explain how the shell relates to the keyboard, the screen, the operating system, and users' programs.
  * Explain when and why command-line interfaces should be used instead of graphical interfaces.
</div>


## What is the Shell?

Humans interact with computers in various ways, including keyboards, mice, touch screens, and speech recognition. The most common method for personal computers is the **graphical user interface** (GUI), where instructions involve clicking a mouse and using menu-driven interactions.

While GUIs are user-friendly, this way of delivering instructions to a computer scales very poorly. Imagine copying the third line from a thousand text files in various directories for a literature search. With a GUI, this would mean hours of repetitive clicking and potential errors. Here's where the Unix shell comes in. It's a **command-line interface** (CLI) and scripting language, creating repetitive tasks to be done automatically and fast. With the proper commands, the shell can repeat tasks easily, making the literature task a matter of seconds.

## The Shell

The shell is a program where users can type and execute commands, from complex tasks like running climate modeling software to simple ones like creating directories with one command. 
The leading Unix shell, Bash (Bourne Again SHell), is the default on modern Unix systems and many Windows packages with Unix-like tools.

Learning the shell requires time and effort. While a GUI presents you with choices to select, CLI choices are not automatically presented to you, similar to learning new vocabulary. However, a small number of "words" (i.e. commands) can get you a long way which we will learn today. 

The grammar of a shell allows you to combine existing tools into powerful
pipelines and handle large volumes of data automatically. Sequences of
commands can be written into a *script*, improving the reproducibility of
workflows.

The command line is the easiest way to interact with remote and supercomputers. Shell proficiency is essential for various specialized tools, including high-performance computing. As clusters and cloud systems rise in scientific data analysis, being able to interact with the shell becomes a necessary skill. These skills enable us to tackle diverse scientific and computational challenges.

Let's get started.

When the shell is first opened, you are presented with a **prompt**,
indicating that the shell is waiting for input.

```bash
$
```

The shell prompt is often `$`, but it may use a different symbol. In our examples, we'll use `$`. When entering commands, *do not type the prompt* and only type the commands that follow it. Remember to press <kbd>Enter</kbd> after typing a command to execute it.

The prompt is followed by a **text cursor** that shows the position where your typing will appear. It often looks like a flashing block, but it can also be an underscore or pipe.

So let's try our first command, `ls` which is short for listing.
This command will list the contents of the current directory:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls
```

Output:

```bash
Desktop     Downloads   Movies      Pictures
Documents   Library     Music       Public
```
</div>


<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note: Command Not Found**
<hr/>
If the shell can't find a program whose name is the command you typed, it
will print an error message such as:

~~~
$ ks
~~~
{: .language-bash}
~~~
ks: command not found
~~~
{: .output}

This might happen if the command was mis-typed or if the program corresponding to that command
is not installed.
</div>

### Nelle's Pipeline: A Typical Problem

Nelle Nemo, a marine biologist,
has just returned from a six-month survey of the
[North Pacific Gyre](http://en.wikipedia.org/wiki/North_Pacific_Gyre),
where she has been sampling gelatinous marine life in the
[Great Pacific Garbage Patch](http://en.wikipedia.org/wiki/Great_Pacific_Garbage_Patch).
She has 1520 samples that she's run through an assay machine to measure the relative abundance
of 300 proteins.
She needs to run these 1520 files through an imaginary program called `goostats.sh` she inherited.
On top of this huge task, she has to write up results by the end of the month so her paper
can appear in a special issue of *Aquatic Goo Letters*.

The downside is that if she has to run `goostats.sh` manually using a GUI, it means she is opening and selecting a file 1520 times. If `goostats.sh` takes 30 seconds to run each file, the whole process will take over 12 hours of Nelle's time. Using the shell, she can delegate this task to her computer while she works on her paper.

The next few lessons will show how Nelle can achieve this. They explain how she can use a command shell to run 'goostats.sh' with loops, automating repetitive steps of entering file names, and allowing her computer to work as she writes her paper.

As a bonus,
once she has put a processing pipeline together,
she will be able to use it again whenever she collects more data.

In order to achieve her task, Nelle needs to know how to:
- navigate to a file/directory
- create a file/directory
- check the length of a file
- chain commands together
- retrieve a set of files
- iterate over files
- run a shell script containing her pipeline

{% include next-button.html
  top-label="Navigating Files and Directories ->"
  bottom-label="2:20pm"
  url="/morea/scientific-software-basics/experience-ssb-filedir.html" %}
