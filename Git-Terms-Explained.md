# Git Terms Explained

A glossary of common Git words
Use this guide to understand what Git commands really mean 

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


Branch

A branch is a separate line of development.
You can safely make changes without affecting the main project.


Main

The main branch is the primary, stable version of your project, the copy everyone trusts.


Origin

Git’s default name for the remote repository you cloned from.
It’s a shorthand reference to the URL of your GitHub repo.


Commit

A commit is a saved snapshot of your changes in time.
Each commit has a message describing what changed.

    git commit -m "Add login form"

Think of it like: hitting “Save” on your progress — but with a note.


Stage (Staging)

When you stage a file, you’re telling Git,
“Hey, I want this file included in my next commit.”

    git add .

Think of it like: putting clothes in a laundry basket —
you haven’t washed (committed) them yet, just decided which ones to include.


Push

Push sends your commits from your local repo → to the remote (GitHub).

    git push origin main

Think of it like: uploading your work to the cloud.


Pull

Pull gets the newest commits from the remote → to your local repo.

    git pull origin main

Think of it like: downloading everyone else’s updates.


Fetch

Fetch checks for new changes from GitHub but doesn’t apply them yet.
You can look before you merge.

Think of it like: reading your mail without opening it yet.


Merge

Merge combines another branch’s changes into your current branch.

    git merge feature/login

Think of it like: mixing two versions of a story into one final draft.


Checkout

Checkout means to switch branches, or to restore a file to a previous state.

    git checkout main

Think of it like: changing which “timeline” you’re viewing.


HEAD

HEAD points to your current position in the project’s history —
usually the latest commit on the branch you’re on.

Think of it like: your current location marker in time.


Untracked Files

Files that exist in your folder but Git hasn’t been told to track yet.

Think of it like: new files that Git doesn’t know about until you git add them.


Clean

To clean means to delete untracked files or folders from your working directory.

    git clean -fd


Think of it like: emptying your workspace trash bin.


Status

Shows you what’s going on — which files are new, changed, staged, or untracked.

    git status

Think of it like: your project’s daily report card.


Global

Global settings apply to all your Git repositories on your computer.
Used mostly for configuration commands.

    git config --global user.name "Your Name"

Think of it like: changing your profile settings, not just one project.


Alias

A shortcut for a longer Git command.
You can make custom abbreviations.

    git config --global alias.co checkout

Think of it like: setting a nickname for a command you use a lot.


Syncing

Syncing means making sure your local and remote repositories have the same content —
by pulling before pushing.

Think of it like: making sure everyone’s files are up to date before saving yours.


Conflict

A merge conflict happens when two people change the same part of a file differently.
Git asks you to decide which version to keep.

Think of it like: two people editing the same sentence in different ways — you need to choose one.


Revert

Revert creates a new commit that undoes a previous one (without erasing history).

    git revert <commit-id>

Think of it like: adding a “reverse” action to your timeline.


Reset

Reset moves your branch back to an earlier commit.
Use carefully — it can change your local history.

Think of it like: rewinding your project’s timeline to an earlier save.


Log

Log shows your project’s commit history.

    git log --oneline

Think of it like: your project’s change diary.


Pull Request (PR)

A Pull Request (or Merge Request) is a GitHub feature —
it lets someone propose merging their branch into another branch.

Think of it like: submitting your work for review before adding it to the main project.


# Summary Table 

| Term | Meaning |
| :---: | :---: |
Local | Your computer
Remote | GitHub copy
Branch | A separate version of the project
Commit | A saved snapshot of your work
Push | Upload commits to GitHub
Pull | Download new commits from GitHub
Merge |	Combine changes from another branch
Fetch |	Check for updates without merging
Checkout | Switch branches or restore files
HEAD | Your current position in history
Untracked | New files Git doesn’t track yet
Clean | Delete untracked files
Status | Show what’s changed
Alias | Shortcut for a Git command
Global | Applies to all repos
Origin | Name of your GitHub remote
Main | Primary branch
Conflict | Two edits on the same line
Revert | Undo a commit by adding a new one
Reset | Move back to an earlier commit
Log | View commit history


License
MIT License — free to use, share, and modify.

Recommended next read:
Git-Quick-Guide.md
