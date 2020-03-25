# practice repo 

#command used 

## Basic Git 
-git init : Create a repo
-git status : compare working directory, staging area, and current branch
-git add x / .(current directory): add changes from stagging area to current branch
-git commit : Commit changes from working directory to staging area
-git config: set or get configuration
-git log : show history of project commits including reference (current branch)

## Git branch
git branch -c first-branch : create new branch
git checkout first-branch : go to branch
git branch : list all the branch
git checkout -b: create and go to new branch


## what is a branch
A branch is a ref(erence) to a commit. When HEAD points to a branch, we say we are on that branch. When we make a commit while we are on a branch, the branch is updated to ref(er) to the new commit.

## What is a HEAD?
HEAD is a ref(erence) to the "current" branch (or sometimes a commit). Git commands like `status`, `log`, and `branch` use HEAD.`git checkout` updates HEAD to ref(er) to a different branch.
