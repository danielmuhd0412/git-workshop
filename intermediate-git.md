---
title: Intermediate Git
layout: default
nav_exclude: true
# nav_order: 3
---

- [Branches](#branches)
- [Merge Conflicts](#merge-conflicts)
- [Further Links](#further-links)

***

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
