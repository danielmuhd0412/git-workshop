---
layout: default
nav_exclude: true
---
# git Exercises Solutions

### 1\. Git Basics

```bash
# create and switch to the folder
$ mkdir git-workshop
$ cd git-workshop

# create the required files
$ touch README.md 
$ touch main.py

# initialise the git repo
$ git init
```

### 2\. Adding & Committing 

```bash
# add files to next commit
$ git add README.md
$ git add main.py

# commit changes
$ git commit -m "Initial commit"
```

### 3\. Branches & Merging

```bash
# create a new branch
$ git branch test

# create another branch
$ git checkout test
$ git branch another

# merge branches
$ git checkout main
$ git merge test
```

### 4\. Merge Conflicts

Resolve the merge conflict as such:

#### before
```py
<<<<<<< HEAD
print("Goodbye")
=======
print("Goodnight")
>>>>>>> test
```

#### after
```py
print("Goodbye")
```