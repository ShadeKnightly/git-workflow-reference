# Git Workflow for Team Projects

This guide explains how to work with branches, commits, and pull requests in a team environment.  

-keep projects organized and collaborative  
-avoid merge conflicts

---

## 1. Update Your Local Main Branch

Before starting any new work, make sure your local `main` branch matches the latest version from GitHub. This ensures you’re building your new work on top of the most recent project code.


            git checkout main
            git fetch origin
            git pull origin main


  ## 2. Create a New Branch for Your WOrk

Each new feature, fix, or update should be done on *ITS OWN BRANCH*, and never directly on main


            git checkout -b [feature/your-branch-name]

 
  Examples of good branch names:
    feature/course-search
    fix/header-navigation
    update/readme-guide
  
  Tip: Use lowercase letters, dashes, and clear purpose-driven names.

  ## 3. Make Changes and Commit Often
  
  After editing or creating files, check your progress and commit regularly.

                # See what changed
              git status
              
              # Stage all changes
              git add .
              
              # Commit with a clear, short message
              git commit -m "Add new course search component"

Commit messages should describe what the change does, not what you did.
For example:
THIS:  “Fix missing student list rendering”
NOT:  “Worked on stuff again”

  ## 4. Keep Your Branch Up to Date with Main
   
While working on your branch, other team members may update main.
To prevent merge conflicts later, regularly pull in those updates
            
            git fetch origin
            git merge origin/main

If conflicts appear:
  Open the files Git marks as conflicted.
  Edit to keep the correct code.
  Save, then run:

            git add .
            git commit

  ## 5. Push Your Branch to GitHub

Once your work is committed locally, push it to GitHub so your teammates can see it.

6. Create a Pull Request (PR)
   
    Go to your project on GitHub.
    You’ll see a message suggesting to “Compare & pull request.” Click it.
    Write a clear title and description for what your branch adds or fixes.
    Assign reviewers if needed.
    Submit the pull request.

7. Review and Merge

After review (or self-checking if you’re working solo):

  ## Make sure your branch can merge cleanly.
  You can test locally before merging:

      git checkout main
      git fetch origin
      git merge --no-commit --no-ff feature/your-branch-name
      git merge --abort  # if just testing
      
Once ready, merge the pull request into main on GitHub.
GitHub will usually offer to delete the branch after merging — confirm this to keep things tidy.

## 8. Pull the Updated Main Branch
After merging your PR, update your local main branch again:

    git checkout main
    git pull origin main

## 9. Clean Up Old Branches Locally

After your work is merged and no longer needed:

    git branch -d feature/your-branch-name

If the branch still exists remotely:
    
    git push origin --delete feature/your-branch-name






======================= COMPLETE WORKFLOW SUMMARY =====================
# 1. Sync main
git checkout main
git pull origin main

# 2. Create a branch
git checkout -b feature/branch-name

# 3. Make changes
git add .
git commit -m "Describe your update"

# 4. Stay updated
git fetch origin
git merge origin/main

# 5. Push to GitHub
git push origin feature/branch-name

# 6. Create and merge Pull Request
# (on GitHub)

# 7. Sync main again
git checkout main
git pull origin main

# 8. Clean up
git branch -d feature/branch-name
git push origin --delete feature/branch-name



=============================================================================================================

****Tips for Smooth Collaboration****

## Never commit directly to main.

## Commit frequently but keep messages meaningful.

## Pull often to avoid large, messy merges.

## Use feature branches for all work — even small fixes.

## Communicate: let others know when you’re merging or rebasing.


============================================================================================================


Optional: Rebasing Instead of Merging
Once your team is comfortable, you can use git rebase instead of git merge to keep history cleaner:

      git fetch origin
      git rebase origin/main
      
If conflicts appear during rebase, fix them and continue with:

      git rebase --continue
      
##  *Only rebase branches that have not yet been shared (not pushed or in active review).*
    

