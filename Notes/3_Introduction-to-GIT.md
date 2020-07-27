# An Introduction to Git

## What is Git?

In a very basic sense, Git is a distributed version-control system for tracking changes in source code during software development.

## Why Git? 

Various global companies like GitHub, GitLab, BitBucket, etc. offer software development and version control using Git.

 - Effective collaboration is the key to any opensource project. 
 
 - Git makes collaboration a lot easier and that is just a speck in its vast multiverse. 
 
 - Ranging from effective collaboration to version-control, Git makes tracking changes in source code a lot easier.

## Basic Terminologies

 - **Repository:** Often referred to as a Repo. This is essentially where the source code (files and folders) reside that we use Git to track.
	
 - **Commit:** Saved changes are called commits. 
 
 - **Branch:** Simply put, a branch in Git is a lightweight movable pointer to one of these commits. The default branch name in Git is master. 
	As we start making commits, we are given a master branch that points to the last commit made.
	
 - **Push:** Pushing is essentially syncing the local repository with remote (accessible over the internet) branches.
 
 - **Merge:** This is pretty much self-explanatory. In a very basic sense, it is integrating two branches together.
 
 - **Clone:** Again cloning is pretty much what it sounds like. It takes the entire remote (accessible over the internet) repository and/or one or more 
	branches and makes it available locally.
	
 - **Fork:** Forking allows us to duplicate an existing repo under our username.

## The Git Workflow: Basics

The three prime states of a local workspace include:

 - **Working directory:** Constitutes all changes we make in our local source code on the repository.
 
 - **Staging area:** All staged files are stored in this tree of the local workspace.
 
 - **Local repo:** All committed files go to this tree of our workspace.
 
Now, pushing the committed changes into your remote repository is essentially required. After all, this is the whole point of Git anyway.

Therefore, simply put, the **Remote Repo** is a common repository that all team members use to collaborate on their changes.

![The Git Workflow](/assignments/summary/assets/git-workflow.jpg)

#### Cloning an existing repository

`git clone <link-to-repository>`

#### List all branches

`git branch`

#### Switching to an existing branch

`git checkout <existing-branch-name>`

#### Creating a new branch

`git checkout -b <new-branch-name>`

#### Adding **all** changes from the working directory to the staging area

`git add .`

#### Committing **all** changes from the staging area to the local repo

`git commit -sm "<commit-message>"`

#### Pushing **all** changes from the local repo to an existing branch in the remote repo

`git push origin <existing-branch-name>`

#### Pull all changes from an existing branch in the remote repo to the local repo

`git pull origin <existing-branch-name>`

#### Compare the working directory with the staging area

`git diff`

#### Compare the working directory and the local repo

`git diff HEAD`
