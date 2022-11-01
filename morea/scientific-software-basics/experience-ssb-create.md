---
title: "3. Working With Files and Directories"
published: true
morea_id: experience-ssb-create
morea_type: experience
morea_summary: "Creating, Copying and Deleting Files"
morea_sort_order: 2
morea_labels:
  - 2:30pm
morea_enable_toc: true
---

# 3. Working With Files and Directories

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
  * How can I create, copy, and delete files and directories?
  * How can I edit files?

**Objectives**
  * Create a directory hierarchy that matches a given diagram.
  * Create files in that hierarchy using an editor or by copying and renaming existing files.
  * Delete, copy and move specified files and/or directories.

**Keypoints**
  * `cp old new` copies a file.
  * `mkdir path` creates a new directory.
  * `mv old new` moves (renames) a file or directory.
  * `rm path` removes (deletes) a file.
  * `-` matches zero or more characters in a filename, so `-.txt` matches all files ending in `.txt`.
  * Use of the Control key may be described in many ways, including `Ctrl-X`, `Control-X`, and `^X`.
  * The shell does not have a trash bin: once something is deleted, it's really gone.
  * Most files' names are `something.extension`. The extension isn't required, and doesn't guarantee anything, but is normally used to indicate the type of data in the file.
  * Depending on the type of work you do, you may need a more powerful text editor than Nano.

</div>

## Creating directories
We now know how to explore files and directories,
but how do we create them in the first place?

### Step one: see where we are and what we already have
Let's go back to our `data-shell` directory on the Desktop
and use `ls -F` to see what it contains:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ pwd
```

Output:

```bash
/Users/nelle/Desktop/data-shell
```
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls -F
```

Output:

```bash
creatures/  data/  molecules/  north-pacific-gyre/  notes.txt  pizza.cfg  solar.pdf  writing/
```
</div>

### Create a directory

Let's create a new directory called `thesis` using the command `mkdir thesis`
(which has no output):

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ mkdir thesis
```

</div>

As you might guess from its name,
`mkdir` means "make directory".
Since `thesis` is a relative path
(i.e., does not have a leading slash, like `/what/ever/thesis`),
the new directory is created in the current working directory:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls -F
```
Output:

```bash
creatures/  data/  molecules/  north-pacific-gyre/  notes.txt  pizza.cfg  solar.pdf  thesis/  writing/
```
</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note: Two ways of doing the same thing**
<hr/>

Using the shell to create a directory is no different than using a file explorer. If you open the current directory using your operating system’s graphical file explorer, the `thesis` directory will appear there too. While the shell and the file explorer are two different ways of interacting with the files, the files and directories themselves are the same.
</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note: Good names for files and directories**
<hr/>

Complicated names of files and directories can make your life painful when working on the command line. Here we provide a few useful tips for the names of your files.

  1. Don’t use spaces.

     Spaces can make a name more meaningful, but since spaces are used to separate arguments on the command line it is better to avoid them in names of files and directories. You can use - or _ instead (e.g. north-pacific-gyre/ rather than north pacific gyre/).

  2. Don’t begin the name with - (dash).

     Commands treat names starting with - as options.

   3. Stick with letters, numbers, . (period or ‘full stop’), - (dash) and _ (underscore).

      Many other characters have special meanings on the command line. We will learn about some of these during this lesson. There are special characters that can cause your command to not work as expected and can even result in data loss.

If you need to refer to names of files or directories that have spaces or other special characters, you should surround the name in quotes ("").
</div>

Since we've just created the `thesis` directory, there's nothing in it yet:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls -F thesis
```
</div>

### Create a text file

Let's change our working directory to `thesis` using `cd`,
then run a text editor called Nano to create a file called `draft.txt`.

On Mana compute nodes do this first:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ module load tools/nano
```
</div>

(The login nodes have the editors, nano, vim and emacs so one can skip the module load above.)

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ cd thesis
$ nano draft.txt
```
</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note: Which Editor?**
<hr/>

When we say, "`nano` is a text editor," we really do mean "text": it can
 only work with plain character data, not tables, images, or any other
 human-friendly media. We use it in examples because it is one of the
 least complex text editors. However, because of this trait, it may
 not be powerful enough or flexible enough for the work you need to do
 after this workshop. On Unix systems (such as Linux and Mac OS X),
 many programmers use [Emacs](http://www.gnu.org/software/emacs/) or
 [Vim](http://www.vim.org/) (both of which require more time to learn),
 or a graphical editor such as
 [Gedit](http://projects.gnome.org/gedit/). On Windows, you may wish to
 use [Notepad++](http://notepad-plus-plus.org/).  Windows also has a built-in
 editor called `notepad` that can be run from the command line in the same
 way as `nano` for the purposes of this lesson.  

 No matter what editor you use, you will need to know where it searches
 for and saves files. If you start it from the shell, it will (probably)
 use your current working directory as its default location. If you use
 your computer's start menu, it may want to save files in your desktop or
 documents directory instead. You can change this by navigating to
 another directory the first time you "Save As..."
</div>

Let's type in a few lines of text.

Once we're happy with our text, we can press <kbd>Ctrl</kbd>+<kbd>O</kbd> (press the Ctrl or Control key and, while
holding it down, press the O key) to write our data to disk
(we'll be asked what file we want to save this to:
press <kbd>Return</kbd> to accept the suggested default of `draft.txt`).

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/nano-screenshot.png" alt="Node anatomy" caption="" %}

Once our file is saved, we can use `Ctrl-X` to quit the editor and
return to the shell.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note: Control, Ctrl, or ^ Key**
<hr/>
The Control key is also called the "Ctrl" key. There are various ways
 in which using the Control key may be described. For example, you may
 see an instruction to press the Control key and, while holding it down,
 press the X key, described as any of:

 * `Control-X`
 * `Control+X`
 * `Ctrl-X`
 * `Ctrl+X`
 * `^X`
 * `C-x`

 In nano, along the bottom of the screen you'll see `^G Get Help ^O WriteOut`.
 This means that you can use `Control-G` to get help and `Control-O` to save your
 file.
</div>

`nano` doesn't leave any output on the screen after it exits,
but `ls` now shows that we have created a file called `draft.txt`:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls
```

Output:

```bash
draft.txt
```
</div>

## Creating Files a Different Way

We have seen how to create text files using the `nano` editor.

Now, try the following command:

<div class="alert alert-secondary" role="alert" markdown="1">
 <i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Try touch**
 <hr/>

Input:

 ```bash
$ touch my_file.txt
 ```

 1.  What did the `touch` command do?
     When you look at your current directory using the GUI file explorer,
     does the file show up?

 2.  Use `ls -l` to inspect the files.  How large is `my_file.txt`?

 3.  When might you want to create a file this way?

 <details markdown="1">
   <summary>Solution</summary>
  1.  The `touch` command generates a new file called `my_file.txt` in
      your current directory.  You
      can observe this newly generated file by typing `ls` at the
      command line prompt.  `my_file.txt` can also be viewed in your
      GUI file explorer.

  2.  When you inspect the file with `ls -l`, note that the size of
      `my_file.txt` is 0 bytes.  In other words, it contains no data.
      If you open `my_file.txt` using your text editor it is blank.

  3.  Some programs do not generate output files themselves, but
      instead require that empty files have already been generated.
      When the program is run, it searches for an existing file to
      populate with its output.  The touch command allows you to
      efficiently generate a blank text file to be used by such
      programs.
   </details>
</div>


## What's in a name?

You may have noticed that all of Nelle's files are named "something dot
 something", and in this part of the lesson, we always used the extension
 `.txt`.  This is just a convention: we can call a file `mythesis` or
 almost anything else we want. However, most people use two-part names
 most of the time to help them (and their programs) tell different kinds
 of files apart. The second part of such a name is called the
 **filename extension**, and indicates
 what type of data the file holds: `.txt` signals a plain text file, `.pdf`
 indicates a PDF document, `.cfg` is a configuration file full of parameters
 for some program or other, `.png` is a PNG image, and so on.

 This is just a convention, albeit an important one. Files contain
 bytes: it's up to us and our programs to interpret those bytes
 according to the rules for plain text files, PDF documents, configuration
 files, images, and so on.

 Naming a PNG image of a whale as `whale.mp3` doesn't somehow
 magically turn it into a recording of whalesong, though it *might*
 cause the operating system to try to open it with a music player
 when someone double-clicks it.


## Moving files and directories
Returning to the `data-shell` directory,

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ cd ~/Desktop/data-shell/
```
</div>

In our `thesis` directory we have a file `draft.txt`
which isn't a particularly informative name,
so let's change the file's name using `mv`,
which is short for "move":

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ mv thesis/draft.txt thesis/quotes.txt
```
</div>

The first argument tells `mv` what we're "moving",
while the second is where it's to go.
In this case,
we're moving `thesis/draft.txt` to `thesis/quotes.txt`,
which has the same effect as renaming the file.
Sure enough,
`ls` shows us that `thesis` now contains one file called `quotes.txt`:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls thesis
```
Output:

```bash
quotes.txt
```
</div>

One has to be careful when specifying the target file name, since `mv` will
silently overwrite any existing file with the same name, which could
lead to data loss. An additional option, `mv -i` (or `mv --interactive`),
can be used to make `mv` ask you for confirmation before overwriting.

Note that `mv` also works on directories.

Let's move `quotes.txt` into the current working directory.
We use `mv` once again,
but this time we'll just use the name of a directory as the second argument
to tell `mv` that we want to keep the filename,
but put the file somewhere new.
(This is why the command is called "move".)
In this case,
the directory name we use is the special directory name `.` that we mentioned earlier.

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ mv thesis/quotes.txt
```
</div>

The effect is to move the file from the directory it was in to the current working directory.
`ls` now shows us that `thesis` is empty:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls thesis
```
</div>


Further,
`ls` with a filename or directory name as an argument only lists that file or directory.
We can use this to see that `quotes.txt` is still in our current directory:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls quotes.txt
```
Output:

```bash
quotes.txt
```
</div>

## Moving to the Current Folder

After running the following commands,
 Jamie realizes that she put the files `sucrose.dat` and `maltose.dat` into the wrong folder:

<div class="alert alert-secondary" role="alert" markdown="1">

```bash
$ ls -F
  analyzed/ raw/
$ ls -F analyzed
 fructose.dat glucose.dat maltose.dat sucrose.dat
$ cd raw/
```
 </div>



 <div class="alert alert-secondary" role="alert" markdown="1">
 <i class="fa-solid fa-user-pen fa-xl"></i> **Exercise: Moving files**
 <hr/>

Fill in the blanks to move these files to the current folder
(i.e., the one she is currently in):

Input:

 ```bash
 $ $ mv ___/sucrose.dat  ___/maltose.dat ___
 ```

<details markdown="1">
<summary>Solution</summary>

```
$ mv ../analyzed/sucrose.dat ../analyzed/maltose.dat .
```
</details>
</div>

Recall that `..` refers to the parent directory (i.e. one above the current directory) and that `.` refers to the current directory.

## Copying files and directories

The `cp` command works very much like `mv`,
except it copies a file instead of moving it.
We can check that it did the right thing using `ls`
with two paths as arguments --- like most Unix commands,
`ls` can be given multiple paths at once:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ cp quotes.txt thesis/quotations.txt
$ ls quotes.txt thesis/quotations.txt
```

Output:

```bash
quotes.txt   thesis/quotations.txt
```
</div>

We can also copy a directory and all its contents by using the
[recursive](https://en.wikipedia.org/wiki/Recursion) option `-r`,
e.g. to back up a directory:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ cp -r thesis thesis_backup
```

</div>

We can check the result by listing the contents of both the `thesis` and `thesis_backup` directory:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls thesis thesis_backup
```
Output:

```bash
thesis:
quotations.txt

thesis_backup:
quotations.txt
```
</div>

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Exercise: Renaming Files**
<hr/>

Suppose that you created a plain-text file in your current directory to contain a list of the
 statistical tests you will need to do to analyze your data, and named it: `statstics.txt`

After creating and saving this file you realize you misspelled the filename! You want to
 correct the mistake, which of the following commands could you use to do so?

 1. `cp statstics.txt statistics.txt`
 2. `mv statstics.txt statistics.txt`
 3. `mv statstics.txt .`
 4. `cp statstics.txt .`


<details markdown="1">
  <summary>Solution</summary>
  1. No.  While this would create a file with the correct name, the incorrectly named file still exists in the directory
    and would need to be deleted.
  2. Yes, this would work to rename the file.
  3. No, the period(.) indicates where to move the file, but does not provide a new file name; identical file names
    cannot be created.
  4. No, the period(.) indicates where to copy the file, but does not provide a new file name; identical file names
    cannot be created.
</details>
</div>

## Moving and Copying

Let's start by assuming the following directory structure situation:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

 ```bash
 $ pwd
 ```

Output:

 ```bash
 /Users/jamie/data
 ```

Input:

```bash
 $ ls
```

Output:

 ```bash
 proteins.dat
 ```
 </div>


<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i> **Exercise: Understanding movement**
<hr/>

Now assume you run the following commands:

```bash
$ mkdir recombine
$ mv proteins.dat recombine/
$ cp recombine/proteins.dat ../proteins-saved.dat
```

Which one of the following would be the output of running the 'ls' command?


1. `proteins-saved.dat recombine`
2. `recombine`
3. `proteins.dat recombine`
4. `proteins-saved.dat`

<details markdown="1">
<summary>Solution</summary>

Let's first recap what the commands did. 

First we start in the '/Users/jamie/data' directory, and create a new folder called 'recombine'.

The second command moves ('mv') the file 'proteins.dat' to the new folder ('recombine').
  
The third command makes a copy of the file we just moved.  The tricky part here is where the file was copied to.  Recall that '..' means "go up a level", so the copied file is now in '/Users/jamie'.
  
Notice that '..' is interpreted with respect to the current working
  directory, **not** with respect to the location of the file being copied.
  So, the only thing that will show using ls (in '/Users/jamie/data') is the recombine folder.

So, here's the answer:

1. No, see explanation above.  'proteins-saved.dat' is located at '/Users/jamie'.
2. Yes.
3. No, see explanation above.  'proteins.dat' is located at '/Users/jamie/data/recombine'
4. No, see explanation above.  'proteins-saved.dat' is located at '/Users/jamie'

</details>
</div>

## Removing files and directories

Returning to the `data-shell` directory,
let's tidy up this directory by removing the `quotes.txt` file we created.
The Unix command we'll use for this is `rm` (short for 'remove'):

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ rm quotes.txt
```
</div>

We can confirm the file has gone using `ls`:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ ls quotes.txt
```
Output:

```bash
cannot access 'quotes.txt': No such file or directory
```
</div>

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-triangle-exclamation fa-xl"></i> **Warning: Deleting Is Forever!!!**
<hr/>

The Unix shell doesn't have a trash bin that we can recover deleted
files from (though most graphical interfaces to Unix do).  Instead,
when we delete files, they are unlinked from the file system so that
their storage space on disk can be recycled. Tools for finding and
recovering deleted files do exist, but there's no guarantee they'll
work in any particular situation, since the computer may recycle the
file's disk space right away.
</div>


<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Using 'rm' Safely**
<hr/>
What happens when we execute `rm -i thesis_backup/quotations.txt`?
Why would we want this protection when using `rm`?

<details markdown="1">
<summary>Answer</summary>
The '-i' option will prompt before (every) removal (use <kbd>Y</kbd> to confirm deletion or <kbd>N</kbd> to keep the file).

The Unix shell doesn't have a trash bin, so all the files removed will disappear forever.

By using the '-i' option, we have the chance to check that we are deleting only the files that we want to remove.
</details>
</div>

If we try to remove the `thesis` directory using `rm thesis`,
we get an error message:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ rm thesis
```

Output:

```bash
rm: cannot remove 'thesis': Is a directory
```
</div>

This happens because `rm` by default only works on files, not directories.

`rm` can remove a directory *and all its contents* if we use the
recursive option `-r`, and it will do so *without any confirmation prompts*:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

```bash
$ rm -r thesis
```
</div>

Given that there is no way to retrieve files deleted using the shell,
`rm -r` *should be used with great caution* (you might consider adding the interactive option `rm -r -i`).

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note: Operations with multiple files and directories**
<hr/>

Oftentimes one needs to copy or move several files at once. This can be done by providing a list of individual filenames, or specifying a naming pattern using wildcards.  
</div>

## Copy with Multiple Filenames

For this exercise, you can test the commands in the `data-shell/data` directory.



<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: cp**
<hr/>

In the example below, what does `cp` do when given several filenames and a directory name?

 ```bash
 $ mkdir backup
 $ cp amino-acids.txt animals.txt backup/
 ```

<details markdown="1">
<summary>Solution</summary>
When the last argument is a directory, `cp` will copy all of the files to that directory.
</details>
</div>


<div class="alert alert-secondary" role="alert" markdown="1">
 <i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: another call to cp**
 <hr/>

Given the following:

```bash
 $  ls -F
```
 
Output:

 ```bash
 amino-acids.txt  animals.txt  backup/  elements/  morse.txt  pdb/  planets.txt  salmon.txt  sunspot.txt
 ```

In the example below, what will `cp` do when given three or more file names?

```bash
$ cp amino-acids.txt animals.txt morse.txt
```

<details markdown="1">
<summary>Solution</summary>

If given more than one file name followed by a directory name (i.e. the destination directory must be the last argument), 'cp' copies the files to the named directory.

If given three file names, 'cp' throws an error such as the one below, because it is expecting a directory name as the last argument:

```bash
cp: target ‘morse.txt’ is not a directory
```
</details>
</div>

### Using wildcards for accessing multiple files at once
 
Note that `*`  is a **wildcard**, which matches zero or more  characters.

Let's consider the `data-shell/molecules` directory:
1. `*.pdb` matches `ethane.pdb`, `propane.pdb`, and every
 file that ends with '.pdb'. 
2. On the other hand, `p*.pdb` only matches
 `pentane.pdb` and `propane.pdb`, because the 'p' at the front only
 matches filenames that begin with the letter 'p'.

The character `?` is also a wildcard, but it matches exactly one character.

So `?ethane.pdb` would match `methane.pdb` whereas
 `*ethane.pdb` matches both `ethane.pdb`, and `methane.pdb`.

Wildcards can be used in combination with each other.

For example, `???ane.pdb` matches three characters followed by `ane.pdb`,
 giving `cubane.pdb  ethane.pdb  octane.pdb`.

When the shell sees a wildcard, it expands the wildcard to create a
 list of matching filenames *before* running the command that was
 asked for. As an exception, if a wildcard expression does not match
 any file, Bash will pass the expression as an argument to the command
 as it is. For example typing `ls *.pdf` in the `molecules` directory
 (which contains only files with names ending with `.pdb`) results in
 an error message that there is no file called `*.pdf`.
 However, generally commands like `wc` and `ls` see the lists of
 file names matching these expressions, but not the wildcards
 themselves. It is the shell, not the other programs, that deals with
 expanding wildcards, and this is another example of orthogonal design.

## List filenames matching a pattern



<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: wildcards**
<hr/>

When run in the `molecules` directory, which `ls` command(s) will
produce this output?

 `ethane.pdb   methane.pdb`

Is the correct command(s):

 1. `ls *t*ane.pdb`
 2. `ls *t?ne.*`
 3. `ls *t??ne.pdb`
 4. `ls ethane.*`

<details markdown="1">
<summary>Solution</summary>
   
The solution is (3)

1. shows all files whose names contain zero or more characters (' * ') followed by the letter 't', then zero or more characters (' * ') followed by 'ane.pdb'. This gives 'ethane.pdb  methane.pdb  octane.pdb  pentane.pdb'.

2. shows all files whose names start with zero or more characters (' * ') followed by the letter 't', then a single character (?), then 'ne.' followed by zero or more characters (' * '). This will give us 'octane.pdb' and 'pentane.pdb' but doesn't match anything which ends in 'thane.pdb'.

3. fixes the problems of option 2 by matching two characters (??) between 't' and 'ne'. This is the solution.

4. only shows files starting with 'ethane.'.
 </details>
 </div>

## More on Wildcards

Sam has a directory containing calibration data, datasets, and descriptions of
 the datasets:

 <div class="alert alert-secondary" role="alert" markdown="1">

 ```bash
 .
 ├── 2015-10-23-calibration.txt
 ├── 2015-10-23-dataset1.txt
 ├── 2015-10-23-dataset2.txt
 ├── 2015-10-23-dataset_overview.txt
 ├── 2015-10-26-calibration.txt
 ├── 2015-10-26-dataset1.txt
 ├── 2015-10-26-dataset2.txt
 ├── 2015-10-26-dataset_overview.txt
 ├── 2015-11-23-calibration.txt
 ├── 2015-11-23-dataset1.txt
 ├── 2015-11-23-dataset2.txt
 ├── 2015-11-23-dataset_overview.txt
 ├── backup
 │   ├── calibration
 │   └── datasets
 └── send_to_bob
     ├── all_datasets_created_on_a_23rd
     └── all_november_files
 ```
 </div>



<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: fill in the blanks**
<hr/>

Before heading off to another field trip, she wants to back up her data and
 send some datasets to her colleague Bob. Sam knows that if she fills in the blanks correctly with the following commands, she can get the job done:

```bash
 $ cp *dataset* backup/datasets
 $ cp ____calibration____ backup/calibration
 $ cp 2015-____-____ send_to_bob/all_november_files/
 $ cp ____ send_to_bob/all_datasets_created_on_a_23rd/
```

Help Sam by filling in the blanks. The resulting directory structure should look like this

 ```bash
 .
 ├── 2015-10-23-calibration.txt
 ├── 2015-10-23-dataset1.txt
 ├── 2015-10-23-dataset2.txt
 ├── 2015-10-23-dataset_overview.txt
 ├── 2015-10-26-calibration.txt
 ├── 2015-10-26-dataset1.txt
 ├── 2015-10-26-dataset2.txt
 ├── 2015-10-26-dataset_overview.txt
 ├── 2015-11-23-calibration.txt
 ├── 2015-11-23-dataset1.txt
 ├── 2015-11-23-dataset2.txt
 ├── 2015-11-23-dataset_overview.txt
 ├── backup
 │   ├── calibration
 │   │   ├── 2015-10-23-calibration.txt
 │   │   ├── 2015-10-26-calibration.txt
 │   │   └── 2015-11-23-calibration.txt
 │   └── datasets
 │       ├── 2015-10-23-dataset1.txt
 │       ├── 2015-10-23-dataset2.txt
 │       ├── 2015-10-23-dataset_overview.txt
 │       ├── 2015-10-26-dataset1.txt
 │       ├── 2015-10-26-dataset2.txt
 │       ├── 2015-10-26-dataset_overview.txt
 │       ├── 2015-11-23-dataset1.txt
 │       ├── 2015-11-23-dataset2.txt
 │       └── 2015-11-23-dataset_overview.txt
 └── send_to_bob
     ├── all_datasets_created_on_a_23rd
     │   ├── 2015-10-23-dataset1.txt
     │   ├── 2015-10-23-dataset2.txt
     │   ├── 2015-10-23-dataset_overview.txt
     │   ├── 2015-11-23-dataset1.txt
     │   ├── 2015-11-23-dataset2.txt
     │   └── 2015-11-23-dataset_overview.txt
     └── all_november_files
         ├── 2015-11-23-calibration.txt
         ├── 2015-11-23-dataset1.txt
         ├── 2015-11-23-dataset2.txt
         └── 2015-11-23-dataset_overview.txt
 ```

<details markdown="1">
<summary>Solution</summary>

```bash
$ cp *calibration.txt backup/calibration
$ cp 2015-11-* send_to_bob/all_november_files/
$ cp *-23-dataset* send_to_bob/all_datasets_created_on_a_23rd/
```
</details>
</div>

## Organizing Directories and Files

Jamie is working on a project and she sees that her files aren't very well
 organized:

<div class="alert alert-secondary" role="alert" markdown="1">

Input:

 ```bash
 $ ls -F
 ```

Output:

 ```bash
 analyzed/  fructose.dat    raw/   sucrose.dat
 ```
 </div>



<div class="alert alert-secondary" role="alert" markdown="1">
 <i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Organizing Files**
 <hr/>

The `fructose.dat` and `sucrose.dat` files contain output from her data
analysis. What command(s) covered in this lesson does she need to run so that the commands below will produce the output shown?

Input:

```bash
 $ ls -F
```

Output:

```bash
 analyzed/   raw/   
```
 
Input:

```bash
 $ ls analyzed
```

Output:

```bash
 fructose.dat    sucrose.dat   
```
<details markdown="1">
<summary>Solution</summary>

```bash
$ mv *.dat analyzed
```

Jamie needs to move her files 'fructose.dat' and 'sucrose.dat' to the 'analyzed' directory.
The shell will expand * .dat to match all .dat files in the current directory.
The 'mv' command then moves the list of .dat files to the "analyzed" directory.
</details>
</div>

## Reproduce a folder structure

You're starting a new experiment, and would like to duplicate the directory
 structure from your previous experiment so you can add new data.

Assume that the previous experiment is in a folder called '2016-05-18',
 which contains a `data` folder that in turn contains folders named `raw` and
 `processed` that contain data files.  The goal is to copy the folder structure
 of the `2016-05-18-data` folder into a folder called `2016-05-20`
 so that your final directory structure looks like this:

<div class="alert alert-secondary" role="alert" markdown="1">


	2016-05-20/
	└── data
	    ├── processed
	    └── raw
 </div>



 <div class="alert alert-secondary" role="alert" markdown="1">
 <i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Reproduce Folder Structure**
 <hr/>

Which of the following sequence of commands would achieve this objective? What would the other sequences do?

Command sequence 1:
 ```bash
 $ mkdir 2016-05-20
 $ mkdir 2016-05-20/data
 $ mkdir 2016-05-20/data/processed
 $ mkdir 2016-05-20/data/raw
 ```

Command sequence 2:
 ```bash
 $ mkdir 2016-05-20
 $ cd 2016-05-20
 $ mkdir data
 $ cd data
 $ mkdir raw processed
 ```

Command sequence 3:
 ```bash
 $ mkdir 2016-05-20/data/raw
 $ mkdir 2016-05-20/data/processed
 ```

Command sequence 4:
 ```bash
 $ mkdir 2016-05-20
 $ cd 2016-05-20
 $ mkdir data
 $ mkdir raw processed
 ```



 <details markdown="1">
<summary>Solution</summary>

The first two command sequences achieve this objective.

The first command sequence uses relative paths to create the top level directory before
   the subdirectories.

The third command sequence will give an error because 'mkdir' won't create a subdirectory
   of a non-existant directory: the intermediate level folders must be created first.

The fourth command sequence generates the 'raw' and 'processed' directories at the same level as the 'data' directory.
 </details>
 </div>

{% include next-button.html
top-label="Pipes and Filters ->"
bottom-label="2:45pm"
url="/morea/scientific-software-basics/experience-ssb-pipefilter.html" %}
