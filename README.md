# practice repo 

#command used 

## Basic Git 
-git init : Create a repo
-git status : compare working directory, staging area, and current branch
-git add x / .(current directory): add changes from stagging area to current branch
-git commit : Commit changes from working directory to staging area
-git config: set or get configuration
-git log : show a history of project commits including reference (current branch)

## Git branch
git branch -c first-branch : create new branch
git checkout first-branch : go to branch (update HEAD)
git branch : list all the branch
git checkout -b: create and go to new branch
git stash : stash changes from working directory (can stash multiple changes at a time)
git stash list : list stashes
git stash pop : apply stashed changes to working directory

## Git Merge
git merge: merge changes from different branches
git log --online --all --graph : get a visualization of all the branches

## what is a branch
A branch is a ref(erence) to a commit. When HEAD points to a branch, we say we are on that branch. When we make a commit while we are on a branch, the branch is updated to ref(er) to the new commit.

## What is a HEAD?
HEAD is a ref(erence) to the "current" branch (or sometimes a commit). Git commands like `status`, `log`, and `branch` use HEAD.`git checkout` updates HEAD to ref(er) to a different branch.

## Merging
Merging means to bring the changes from one branch to another.

A fast forward merge happen when the target branch was branched from the current one, and there are no new changes to the current branch since then. 
