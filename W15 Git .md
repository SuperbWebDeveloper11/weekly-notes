# `Git Version Control System`

## `The following notes are covered in this file`

- Introduction
- Installing git
- Checkout git version
- Initialize a git repository
- Staging area
- configure Git and link it to GitHub
- Commiting
- Synchronizing your local Git repository with GitHub

## `Introduction`

Git is a Version Control System

## `Installing git`

```bash
sudo apt-get install git
```

## `Checkout git version`

```bash
git --version
```

## `Initialize a git repository`

```bash
git init
```

## `Staging area`

```bash
# Check the staging area
git status
# Stages all changes
git add -A
# Stages new files and modifications, without deletions
git add .
# Stages modifications and deletions, without new files
git add -u
```

## `configure Git and link it to GitHub`

```bash
git config --global user.name "USERNAME"
git config --global user.email "EMAIL"
```

## `Commiting`

```bash
# commit new changes
git commit -m 'Initial commit'
# List all the commits you have made with the comments that you specified
git log
```

## `Synchronizing your local Git repository with GitHub`

```bash
git remote add origin https://github.com/Moonapnd/my-notes.git
# push your repository to GitHub
git push -u origin Main
```
