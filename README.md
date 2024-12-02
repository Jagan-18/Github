# Github

## Commands list to push & Pull code to New repository.
*******************************************************

#create a new repository on the command line:
=============================================
1. git init
2. git add README.md
3. git commit -m "first commit"
4. git branch -M main
5. git remote add origin https://github.com/Jagan-18/Netflix-clone.git
6. git push -u origin main




#push an existing repository from the command line:
====================================================
1. git init
2. git add .
3. git commit -m "Push existing project to GitLab"
4. git remote add origin https://github.com/Jagan-18/Netflix-clone.git
5. git branch -M main
6. git push -u origin main
7. git push -u origin main




#GitHub Commands list to pull code to Github Repo.
---------------------------------------------------

1. git init
2. git add .
3. git commit -m "Commit message"
4. git branch -M main or (if case you want to pull other branch give that branch-name)
5. git remote add origin <GitHub link>
6. git push -u origin main

 ===>#while pull code in main branch get any error (error: failed to push some refs to <Git-url>)]
 
7. creating othere git branch and pull code to there.

   ==> git checkout -b <New-BranchName>
8. git add .
9. git commit -m "commit message"
10. git push -u origin <New BranchName>

-------------------------------------------------------------------------------------------------------------
# Error while push code in repo: flowinf steps:
 #### ! [rejected]        main -> main (non-fast-forward) error: failed to push some refs to "<Github_URL>"
```bash
git rebase --continue
git add .
git rebase --continue
git fetch origin  # After finishing the rebase, make sure that your local branch is up-to-date with the remote branch.
git push origin main
```
