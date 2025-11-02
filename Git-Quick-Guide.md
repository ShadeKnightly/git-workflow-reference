
# Quick Start Guide

A reference for everyday Git commands.  
For new developers learning to work with branches, commits, and pull requests.

---

## Setup

Clone a repository from GitHub to your computer:

    git clone htps://github.com/your-username/project-name.git
    cd project-name


Check what branch you’re on:

    git branch


List all remote branches:

    git branch -r


# Keeping Up to Date

Always make sure you have the latest version of the code:

    git fetch origin
    git pull origin main

    
# Branching

Create a new branch:

    git checkout -b feature/branch-name


Switch to an existing branch:

    git checkout branch-name


Delete a branch (locally):

    git branch -d branch-name


Delete a remote branch:

    git push origin --delete branch-name


# Working with Changes

Check what’s changed:

    git status


See differences before committing:

    git diff


Stage all changes:

    git add .


Commit your changes with a clear message:

    git commit -m "Describe what this change does"


Undo staging (unstage files):

    git reset HEAD <file>


Discard local changes (careful!):

    git checkout -- <file>


# Syncing with Remote

Push your branch to GitHub:

      git push origin branch-name


Pull the latest updates for your current branch:

    git pull


# Merging

Switch to main, make sure it’s up to date, then merge another branch:

    git checkout main
    git pull origin main
    git merge feature/branch-name


If everything looks good, commit and push:

    git push origin main


# Checking Merge Compatibility (Dry Run)

Test if a branch can merge cleanly without making changes:

    git fetch origin
    git merge --no-commit --no-ff feature/branch-name
    git merge --abort


# Logs and History

View commit history:

    git log --oneline


See who changed a specific file:

    git blame filename.js


Show the last commit:

    git show


# Fixing Common Mistakes

Undo your last commit but keep changes:

    git reset --soft HEAD~1


Undo last commit completely:

    git reset --hard HEAD~1


Undo local changes (restore file to last commit):

    git checkout -- filename


# Clean Up

Remove untracked files and folders (use carefully):

    git clean -fd


# Helpful Aliases (Optional)

Speed up common commands by setting Git aliases:

    git config --global alias.co checkout
    git config --global alias.br branch
    git config --global alias.cm commit
    git config --global alias.st status


Then you can use commands like:

    git co main
    git br
    git cm -m "message"
    git st


# Quick Reference Summary

| Action | Command |
|    :---:    |    :---:    |
| Clone a repo | git clone <url> 
| Create a branch | git checkout -b <branch> 
| Switch branch | git checkout <branch>
| Stage changes |	git add .
| Commit | git commit -m "message"
| Push | git push origin <branch>
| Pull | git pull
| Merge |	git merge <branch>
| See history | git log --oneline
| Undo last commit | git reset --soft HEAD~1


# Recommended next read:
Git Workflow for Team Projects
  
