# Practice Repository -Github commands 

## Basic Git 
- `git init` : Create a repo
- `git status` : compare working directory, staging area, and current branch
- `git add x / .(current directory)` : add changes from stagging area to current branch
- `git commit` : Commit changes from working directory to staging area
- `git config` : set or get configuration
- `git log` : show a history of project commits including reference (current branch)

## Git branch
- `git branch -c first-branch` : create new branch
- `git checkout first-branch` : go to branch (update HEAD)
- `git branch` : list all the branch
- `git checkout -b` : create and go to new branch
- `git stash` : stash changes from working directory (can stash multiple changes at a time)
- `git stash list` : list stashes
- `git stash pop` : apply stashed changes to working directory

## Git Merge
- `git merge` : merge changes from different branches
- `git diff` : show difference before and after edit 
- `git log --online --all --graph` : get a visualization of all the branches
- `git merge --abort` : abort an in-progress merge
- `git log <branch1>..<branch2>` --oneline : log of commits in branch 2 that dont exist in branch 1
- `git log <branch1>...<branch2>` : log of commits in either branch but not both 
- `git merge --no-commit --no-ff new-branch` : attempt to merge but do not create an auto merge or ff merge
- `git branch --no-merged master` : list all the branch with commits that have not merged with master
- `git branch --merged branch1` : list branches with no unmerged commits

## Git log
- `git log <ref>` : show history of project commits prior to <ref> where ref can be a branch or commit
- `git log --all` : show all commit
- `git log --author "X"` : show commit with mathing author
- `git log --since "6 months ago"` : show commits since date
- `git log --until "Aug 21"` : shows commits prior to date
- `git log --oneline` : show one commit per line
- `git log --graph` : show graph view of commits
- `git show <commit>` : show differences introduced by commit
- `git show` : show a single commit
- `git diff` : show the difference between commits, the working directory and the staging area
- `git diff <commit>` : show difference between working dir and commit
- `git diff --cached` : difference between staging area and HEAD
- `git diff --cached <commit>` : difference between staging area and commit
- `git diff <commitA>..<commitB>` : Difference between commits
- `git diff <refA>..<refB>` : Difference between refs (branches, et al)
  
## Git Remote
- `git remote add <remote> <url>` : add a new <remote> at <url>
- `git remote -v` : list remote repositories
- `git push -u <remote> <branch>` : push <branch> to <remote>, and set default upstream for <branch>
- `git fetch` : fetch changes from remote repository
- `git pull` : fetch and then merge
- `git push <remote> <branch>` : push branch to <remote>
  
## Connecting console to github repo
1. open Git bash
2. generate ssh public and private key
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
3. enter file location and passphrase
- e.g. private key saved in /c/Users/lik.hui.kong/.ssh/id_rsa.pub
- e.g. key fingerprint : SHA256:S1ScKCUMljCpvW0Sy9ibJJqhRWXZbbimivwaw2KhvDM lik.hui.kong@accenture.com
4. add ssh key to ssh-agent\
#start the ssh-agent in the background\
$ eval $(ssh-agent -s)\
#add ssh private key to ssh-agent\
$ ssh-add ~/.ssh/id_rsa
5. add shh key to github account
#Copy the SSH key to your clipboard\
$ clip < ~/.ssh/id_rsa.pub\
#go to setting on Github and add ssh keys
6. ssh to github
#Attempts to ssh to GitHub\
$ ssh -T git@github.com

## What is a branch?
A branch is a ref(erence) to a commit. When HEAD points to a branch, we say we are on that branch. When we make a commit while we are on a branch, the branch is updated to ref(er) to the new commit.

## What is a HEAD?
HEAD is a ref(erence) to the "current" branch (or sometimes a commit). Git commands like `status`, `log`, and `branch` use HEAD.`git checkout` updates HEAD to ref(er) to a different branch.

## Merging
Merging means to bring the changes from one branch to another.

A fast forward merge happen when the target branch was branched from the current one, and there are no new changes to the current branch since then.

An automatic merge happens when the two histories have diverged, but git is able to reconcile them into one set of changes. This creates a new commit on the current branch. 

## Resolving a Merge conflict 
1. Don't panic!
2. Edit files to resolve conflict
3. Add changes to staging area with `git add`
4. Commit changes with `git commit`

## What is a remote?
A remote repo is one hosted somewhere other than one's machine. We can add remotes with `git remote add`, and set up *tracking branches* to track differences between our local and remote repositories

We push to remotes with `git push`, and fetch from them with `git fetch`. We can also fetch and merge in one set with `git pull`.

## Sync github remote repo changes on local repository
After changes has been made on remote repo, use `git fetch` will fetch the changes but `git log` will not show the changes yet. A `git merge` is required to register the commit on the logs on the local repo. `git pull` can replace `git fetch` and `git merge` so that the sync can be done with just one command
