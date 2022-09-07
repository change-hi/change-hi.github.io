---
title: "Local Repository Directory Path: No Spaces!"
published: true
morea_id: reading-local-repository-directory-path
morea_summary: "No spaces in the path to your local git repositories"
morea_type: reading
morea_sort_order: 6
---

# Make sure the path to your local repositories does not contain spaces!

Part of using GitHub is maintaining local copies of repositories in your laptop's file system.

To avoid a variety of difficult to debug problems later on, you should make sure that the fully qualified path to your local repositories does not contain any spaces.

This often happens when you create a directory to hold your GitHub repositories inside your home directory, and your home directory contains spaces.  Here's an example from a Windows user:

```
C:\Users\Jayson P\Documents\GitHub\react-tic-tac-toe
```

This user has cloned the repo "react-tic-tac-toe" into their GitHub directory, but inspection of their full path reveals that a higher level directory in that path has a space ("Jayson P").

The fix is to move the directory containing your GitHub repos to a location where the full path does not contain spaces. On Windows, you could just move it to C:\, so the full path would now look like:

```
C:\GitHub\react-tic-tac-toe
```

On a Mac or Unix system, the home directory generally doesn't contain spaces, so if there's a space in your path, you just need to move the directory to a different location inside your home directory. For example, you don't want to put your GitHub directory within the "Google Drive" directory:

```
/Users/jaysonp/Google Drive/github/react-tic-tac-toe
```

The solution in this case is to simply move the github directory into your home directory:

```
/Users/jaysonp/github/react-tic-tac-toe
```
### How to find the full path?

First, navigate in a command shell to the directory containing your GitHub repositories. Then, to show the full path to the current directory, enter `cd` on Windows or `pwd` on Mac or Unix.








