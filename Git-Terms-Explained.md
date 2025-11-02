# Git Terms Explained

A glossary of common Git words

---

## Repository (Repo)
A **repository** is your project’s folder that Git is tracking.  
It contains all your files, folders, and the full history of changes.

---

## Local vs Remote

- **Local** = On *your* computer.  
- **Remote** = On *GitHub* (the shared version everyone can access).

Example:  
You clone a GitHub repo --> now you have a *local copy* on your computer.  
You push changes → you’re sending your changes *back* to the remote.

---

## Clone
To **clone** means to make a copy of a GitHub repository on your computer.
This downloads the full project and its history.

    git clone https://github.com/example/project.git

---

## Branch

A branch is a separate line of development.
You can safely make changes without affecting the main project.

---

## Main

The main branch is the primary, stable version of your project, the copy everyone trusts.

---

## Origin

Git’s default name for the remote repository you cloned from.
It’s a shorthand reference to the URL of your GitHub repo.

---

## Commit

A commit is a saved snapshot of your code in your local repository.
Commits exist only on your computer until you push them to the remote repo.
Each commit includes a message describing what and why you changed something.

    git commit -m "Fix course search button alignment"
    
---

## Stage (Staging)

When you stage a file, you’re telling Git to included it in your next commit

    git add .

---

## Push

Push sends your commits from your local branch to the same branch on the remote repository (On Github)
This doesn’t necessarily mean you’re pushing to main — it only pushes to the remote version of whatever branch you’re on.
Each developer usually works in and pushes their own feature branch, and later merges it into main through a pull request. 

# Push the branch you're currently on
    git push origin <branch-name>

# Example: pushing main
    git push origin main
---

## Pull

Pull gets the newest commits from the remote → to your local repo.

    git pull origin main

Think of it like: downloading everyone else’s updates.

---

## Fetch

CHecks for updates from the remote repository without changing your local files or branches.

For example, this command contacts the remote (usually GitHub, called origin) and downloads updates for all branches, not just the one you’re currently on.

    git fetch origin
    
--> Fetches new commits, branches, and tags from the entire origin repository.
--> Updates your remote-tracking branches (like origin/main, origin/dev, etc.).

*It Does not touch your current working files or local branches.*

# Example

Let's say your repo has these branches: 
main
feature/login
feature/courses

and let's say you're currently on the feature/courses branch.
If someone updates feature/login on Github, and someone else updates feature/courses and you run: 

    git fetch origin
    
Git will update your local copy of origin/main with those new commmits that both of those people made (Without merging them into your *local* branch)

# Fetch a specific Branch

You can also fetch just one branch    

So, given the same example, if you instead run 
    
    git fetch origin feature/login

This will opnly update your local reference to the feature/login branch (not all branches).

## What is this 'local reference'? 

When you fetch updates for another branch, those updates are downloaded to a *remote-tracking branch*.
In this example it would be called "origin/feature/login". 

That means:

- origin/feature/login now represents what’s on GitHub.

- Your local feature/login branch (if you have one) still represents your older local copy.


## To see or use the updates, 

1.  Switch to that branch and merge its remote version
   
   If you have a local branch with the same name, 

        git checkout feature/login       # switch to the local branch
        git merge origin/feature/login   # update your local branch with the newest commits from GitHub

--> this updates your local feature/login branch with the latest commits from origin/feature/login (the remote copy on Github)


2. Pull Directly
   If you just want to bring the remote updates into your local branch in one step (a fetch + merge combined)

        git checkout feature/login
        git pull origin feature/login

## Summary

| Goal | Command(s) | What Happens |
| :---: | :---: | :---: |
Check for updates | git fetch origin feature/login | Downloads new commits only
Update your local branch manually | git merge origin/feature/login | Combines remote updates into your branch
Update automatically | git pull origin feature/login | Fetches and merges in one step

---

## Merge

Merge combines another branch’s changes into your current branch.

    git merge feature/login

Think of it like: mixing two versions of a story into one final draft.

---

## Checkout

Checkout means to switch branches, or to restore a file to a previous state.

    git checkout main

Think of it like: changing which “timeline” you’re viewing.

---

## HEAD

HEAD points to your current position in the project’s history —
usually the latest commit on the branch you’re on.

Think of it like: your current location marker in time.

---

## Untracked Files

Files that exist in your folder but Git hasn’t been told to track yet.

Think of it like: new files that Git doesn’t know about until you git add them.

---

## Clean

To clean means to delete untracked files or folders from your working directory.

    git clean -fd


Think of it like: emptying your workspace trash bin.

---

## Status

Shows you what’s going on — which files are new, changed, staged, or untracked.

    git status

Think of it like: your project’s daily report card.

---

## Global

Global settings apply to all your Git repositories on your computer.
Used mostly for configuration commands.

    git config --global user.name "Your Name"

Think of it like: changing your profile settings, not just one project.

---

## Alias

A shortcut for a longer Git command.
You can make custom abbreviations.

    git config --global alias.co checkout

Think of it like: setting a nickname for a command you use a lot.

---

## Syncing

Syncing means making sure your local and remote repositories have the same content —
by pulling before pushing.

Think of it like: making sure everyone’s files are up to date before saving yours.

---

## Conflict

A merge conflict happens when two people change the same part of a file differently.
Git asks you to decide which version to keep.

Think of it like: two people editing the same sentence in different ways — you need to choose one.

---

## Revert

Revert creates a new commit that undoes a previous one (without erasing history).

    git revert <commit-id>

Think of it like: adding a “reverse” action to your timeline.

---

## Reset

Reset moves your branch back to an earlier commit.
Use carefully — it can change your local history.

Think of it like: rewinding your project’s timeline to an earlier save.

--- 

## Log

Log shows your project’s commit history.

    git log --oneline

Think of it like: your project’s change diary.

--- 

## Pull Request (PR)

A Pull Request (or Merge Request) is a GitHub feature —
it lets someone propose merging their branch into another branch.

Think of it like: submitting your work for review before adding it to the main project.

--- 

# Summary Table 

---

| Term | Meaning | Example |
| :---: | :--- | :--- |
| Repository | Project folder tracked by Git with code history | Local repo: `C:\Projects\MyApp` |
| Local | Your copy of the repo on your computer | `C:\Projects\MyApp` |
| Remote | Shared version of the repo on GitHub | `https://github.com/your-username/MyApp` |
| Clone | Copy a remote repo to your computer | `git clone https://github.com/example/project.git` |
| Branch | A separate version of the project for new work | `git checkout -b new-feature` |
| Commit | A saved snapshot of your changes | `git commit -m "Add login form"` |
| Push | Send commits to the remote repo | `git push origin new-feature` |
| Pull | Get and merge updates from remote | `git pull origin main` |
| Merge | Combine another branch into yours | `git merge new-feature` |
| Fetch | Get updates from remote without merging | `git fetch origin` |
| Checkout | Switch branches or restore files | `git checkout main` |
| HEAD | Shows your current branch or commit | `HEAD -> main` |
| Untracked | Files not yet added to Git | Shown in `git status` before `git add` |
| Clean | No uncommitted or untracked changes | “nothing to commit, working tree clean” |
| Status | Show what’s changed or staged | `git status` |
| Alias | Shortcut for a Git command | `git config --global alias.co checkout` |
| Global | Setting that applies to all repos | `git config --global user.name "Your Name"` |
| Origin | Default name for your remote repo | `git push origin main` |
| Main | Primary branch for stable code | `git checkout main` |
| Conflict | When Git can’t auto-merge edits | Happens during `git merge` |
| Revert | Undo a commit with a new one | `git revert <commit-id>` |
| Reset | Move branch to an earlier commit | `git reset --hard <commit-id>` |
| Log | View commit history | `git log --oneline` |


License
MIT License — free to use, share, and modify.

Recommended next read:
Git-Quick-Guide.md
