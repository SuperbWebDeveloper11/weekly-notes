# Git Version Control System

## `Installing git`

sudo apt-get install git

## `Checkout git version`

git --version

## `Initialize a git repository`

git init

## `Staging area`

**git status** check the staging area
**git add -A** stages all changes
**git add .** stages new files and modifications, without deletions
**git add -u** stages modifications and deletions, without new files

## `configure Git and link it to GitHub`

git config --global user.name "USERNAME"
git config --global user.email "EMAIL"

## `Commiting`

Having specified that the file should be tracked, we need to tell Git that we have made changes to the file that we want it to record

**git commit -m 'Initial commit'**

To find out whether there are any files that are not being tracked by Git or whether there are files that are being tracked that haven’t been committed

**git status**

git log : (This will list all the commits you have made with the comments that you specified)

commit 1cdde6a9b85cb7210f9fbc67b1ac88ac70281981 (HEAD -> master)
Author: moonapnd <moonapnd@gmail.com>
Date: Sun Mar 8 20:25:04 2020 +0100

    second commit

commit 124d8cc87a64f54617b589bf43696ddc6c65e92a
Author: moonapnd <moonapnd@gmail.com>
Date: Sun Mar 8 20:18:04 2020 +0100

    Initial notes

- Synchronizing your local Git repository with GitHub
  git remote add origin https://github.com/Moonapnd/my-notes.git
  git push -u origin master (next time just tipe -git push- )

- Deleting and renaming files:

Normally you would delete a file with rm and rename or move a file using mv. However, we also need to tell Git that we have deleted, renamed or moved a file. To do that we have to remember to delete, rename or move the file via Git.
Do not do this now, but if, for example, we wished to rename our proteins.txt file to proteininfo.txt we would do:

git mv proteins.txt proteininfo.txt

Similarly to delete a file and stop Git from tracking it we would do:
git rm proteins.txt

- undoing changes before commiting:
  if you make some changes and you didn't commited those changes yet you can undoing thees changes
  ( reset everything to the last commit)
  git reset --hard

- undoing changes after commiting:
  Suppose however that you have committed a change and now want to undo that change and revert to the previous version. You will recall that when you use git log you are shown the comments, but also shown lines saying commit with some apparently random set of letters and numbers. This is an identifier for a particular commit. We can use git revert with one of these identifiers to remove the changhed that happened in that commit. In practice, you only need about the first 6 or 7 characters of the commit identifier to identify a particular commit uniquely.

git revert adbd940

# Removed folder from repository without deleting from local system

git rm -r --cached FolderName
git commit -m "Removed folder from repository"
git push origin master

# Removed folder from repository without deleting from local system

git rm -r one-of-the-directories // This deletes from filesystem
git commit . -m "Remove duplicated directory"
git push origin <your-git-branch> (typically 'master', but not always)
