---
layout: default
nav_order: 3
---
# Intro to Git

- [Intro to Git](#intro-to-git)
  - [What is a Git Repository?](#what-is-a-git-repository)
  - [Configuring Git](#configuring-git)
  - [Getting a Git Repository](#getting-a-git-repository)
  - [Creating a Basic Git Repo](#creating-a-basic-git-repo)
  - [Best Practices](#best-practices)
  - [Adding, Staging, Committing](#adding-staging-committing)
  - [Working With Remote Repositories](#working-with-remote-repositories)
  - [Cloning a Repo](#cloning-a-repo)
  - [Pushing to a Remote](#pushing-to-a-remote)
  - [Pulling from a Remote](#pulling-from-a-remote)
  - [Linking a Local Repo to a Remote](#linking-a-local-repo-to-a-remote)
  - [Branches](#branches)
  - [Merge Conflicts](#merge-conflicts)
  - [Further Links](#further-links)

***

## What is a Git Repository?

A repository tracks all changes made to files in a project by saving snapshots of the project's history.

It is represented by the `.git` folder in the filesystem, and is also known as a **repo** for short.

***

## Configuring Git

When using Git for the first time, you need to set your **name** and **e-mail**.

Git uses this to identify who you are.

```bash
# set your name
git config --global user.name "your_name"

# set your email-address
git config --global user.email "your_email"

# makes command line output colorful (increases readability)
git config --global color.ui auto
```

## Getting a Git Repository

Method 1: Creating a repo from an existing directory

```text
git init
```

Method 2: Copying a repo from another source (see [Remotes](#linking-a-local-repo-to-a-remote))

```text
git clone
```

## Creating a Basic Git Repo

```bash
# create an empty directory named git-workshop
mkdir git-workshop

# navigate to the directory
cd git-workshop

# initialise an empty repo
git init

# confirm that repo exists
git status
```

## Best Practices

After creating a new repo, you should do the following:

a. Add a README file

- a README is a short description of your project
- refer to [Make a README](https://www.makeareadme.com/) for a guide on creating a basic README

b. Add a .gitignore file

- a .gitignore file tells git to not track specified files
- refer to [GitHub's .gitignore Templates](https://github.com/github/gitignore) for a set of ready-made .gitignore files

## Adding, Staging, Committing

When you add a file, Git begins to track it.

A similar analogy would be adding items to a package that you want to mail to someone else later.

```bash
# creating a README in UNIX (Mac/Linux) 
touch README
echo "git-workshop" >> README

# creating a README in Windows
# use the file explorer to create a txt!

# is Git tracking the README?
git status

# add README to the staging area so that Git can track it 
git add README

# was the README added?
git status
```

What about adding multiple files?

```bash
# of course, you can do it the painful way
git add file1
git add folder\file2

...

# there is however an easier way!

# the dot tells Git to add *everything* in the directory 
git add .

# *everything* includes files in subfolders too
```

Once you're done adding files, it's time to make a commit.

A commit is a snapshot of the current state of the repo.

Following the previous analogy, you are sealing and sending the package.

```bash
# the -m flag allows you to add a message to your commit 
git commit -m "added README"

# how does the repo look like now?
git status

# check commit history
git log
```

***

## Working With Remote Repositories

So far, we have only been working on our local machine.
These are local repos.

What if we wanted to work on someone else's repo?
Or if we wanted to host our repo online to let others collaborate?

We do that by utilising remote repos.

## Cloning a Repo

By cloning a repo, you are essentially copying a repo from an external source.
A directory created with all the files from the project after cloning.

What are external sources?
These are repos hosted on the web through platforms such as GitHub or Gitlab.

The two main ways to clone a repo are with either HTTP or SSH.
These methods are essentially the same for our purposes. We will be using HTTP.

To get the URL, click on the green `CODE` button on a GitHub repo (`CLONE` on Gitlab).

Copy the URL shown under the HTTPS tab.

```bash
# clone a repo 
git clone <url_for_remote_repo>

# navigate to the repo's folder
cd folder-name
```

## Pushing to a Remote

Pushing = Adding the local commits you made to the project to the remote repo.

```bash
git push <remote> <branch>
```

## Pulling from a Remote

Pulling = Updates the local copy with new changes from the remote.

There are 2 ways to do this.

```bash
# downloads all changes, but does not combine the changes to your local copy
git fetch

# combines changes into local copy
git merge

# both fetch and merge in one command
git pull
```

## Linking a Local Repo to a Remote

```bash
# add remote repo url to local repo
git remote add origin [url]

# at this point you might be prompted to authenticate with GitHub/GitLab

# push and create corresponding branch in remote
git push --set-upstream origin main
```

## Branches

A branch is a copy of the current repo with its own commit history.
It is mostly used to code new features or fix bugs without affecting the original code.

```bash
# list all available branches
git branch

# create a branch with name "test"
git branch test

# switch to test branch
git checkout test

# delete test branch
git branch -d test

# create and switch to test branch
git checkout -b test
```

## Merge Conflicts

Merge conflicts occur when Git cannot automatically resolve the changes made to the repo.

These typically occur when:
1\. 2 branches are merged.
2\. The remote repo differs largely from the local repo.

When this happens, we need to go into the files and fix the conflict manually.

```bash
# try to merge test branch with current branch
git merge test

# which files have a merge conflict?
git status
```

## Further Links

[Pro Git](https://git-scm.com/book/en/v2) - A book that goes in-depth on everything Git has to offer.

[Oh Shit, Git!?!](https://ohshitgit.com/) - For times when you screw up and don't know what to do.

[GitHub's .gitignore Templates](https://github.com/github/gitignore) - .gitignore templates from Github.
