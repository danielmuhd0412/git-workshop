---
layout: default
nav_order: 4
---
# git Exercises

### 1\. Git Basics

a\. Create a new folder named `git-workshop` on your computer. The folder should contain the following files:

- `README.md`
- `main.py`

b\. Change to the directory with the `cd` command.

c\. Initialise a git repository for the folder.

> Tip: `.md` and `.py` files are plain text files. Text editors like Notepad and TextEdit can create, open, and modify such files.

### 2\. Adding & Committing 

a\. Add the following code to `main.py`.
```py
print("Hello World!")
```

b\. Add the following text to `README.md`.
```
# README

This is a README.
```

c\. Commit these changes with the commit message `Initial commit`.

### 3\. Branches & Merging

a\. Create a new branch named `test`.

b\. Change `main.py` in the `test` branch so that `Bonjour` is printed instead of `Hello World!`.

c\. Commit these changes.

> Tip: You may have realised by now that working with git is a cycle of making changes to files, then a `git add`, and finally a `git commit`. 

d\. Create a new branch named `another` **which is derived from the `test` branch**. 

e\. Change `main.py` in the `another` branch so that `Good Morning` is the output.

f\. Commit these changes.

g\. Merge the `main` branch with the `test` branch.

> Tip: `git add .` adds all modified files to the next commit.

### 4\. Merge Conflicts

a\. Change `main.py` in the `test` branch so that `Goodnight` is the output. Commit these changes.

b\. Change `main.py` in the `main` branch so that `Goodbye` is the output. Commit these changes.

c\. Merge the `main` branch with the `test` branch.

d\. Resolve the merge conflict by changing the output to `Goodbye`.

### 5\. Remotes & Issues (OPTIONAL)

a\. Upload your repository to a remote server. It can either be GitHub or GitLab.

b\. Create a new issue for the remote repository. 

