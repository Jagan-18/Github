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
 git fetch origin
```
```bash
git rebase origin/main
git add .
git rebase --continue
git fetch origin  # After finishing the rebase, make sure that your local branch is up-to-date with the remote branch.
git push origin main
```

Certainly! Here's a well-structured and formatted way to add the Git-related interview questions and answers to your **README file**:

---

# Git Interview Questions 

## 1. **How do you handle merge conflicts in Git?**
   **Answer**:  
   To handle merge conflicts, follow these steps:
   - Use `git status` to identify the conflicting files.
   - Open the files and manually resolve the conflicts by deciding which version of the code to keep.
   - After resolving conflicts, mark the file as resolved with `git add <file_name>`.
   - Commit the merge using `git commit`. This will record the conflict resolution in the history.

## 2. **What is the difference between `git merge` and `git rebase`?**
   **Answer**:
   - **`git merge`** combines two branches and creates a merge commit, preserving the history.
   - **`git rebase`** moves or reapplies commits from one branch onto another, resulting in a linear commit history without a merge commit.

   **When to use**:  
   - Use `merge` to preserve history with all commits.
   - Use `rebase` to clean up commit history and avoid unnecessary merge commits.

## 3. **What is GitFlow, and how do you use it in a DevOps pipeline?**
   **Answer**:  
   **GitFlow** is a branching model with structured workflows:
   - `master`: Stores production-ready code.
   - `develop`: Ongoing development.
   - `feature`: Branches for specific features.
   - `release`: Prepares code for production.
   - `hotfix`: For urgent fixes in production.

   In a DevOps pipeline, GitFlow helps manage feature development, staging, and hotfixes with clear separation and automation via CI/CD tools.

## 4. **How do you automate versioning and tagging in a Git repository?**
   **Answer**:  
   - Use `git tag` to manually mark specific commits as release points.
   - Automate tagging through CI/CD pipelines, where tags are created automatically when code is merged into the `master` branch (e.g., `v1.0.0`).
   - Tools like **Semantic Versioning** can automate versioning during the release process based on commit history.

## 5. **Explain how Git integrates with a CI/CD pipeline.**
   **Answer**:  
   Git integrates into CI/CD pipelines by triggering build and deployment processes. When changes are pushed to Git:
   - CI tools (Jenkins, GitLab CI, etc.) pull the latest code from the repository.
   - Automated tests, builds, and deployments are executed.
   - Git branches can be linked to specific environments (e.g., `dev`, `staging`, `prod`).

## 6. **What is a Git submodule, and how would you use it in a project?**
   **Answer**:  
   A **Git submodule** allows you to include a Git repository inside another Git repository. It’s useful for managing external dependencies or libraries.
   - Use `git submodule add <repository_url>` to include a submodule.
   - Manage updates with `git submodule update`.

## 7. **How would you automate deployment using Git?**
   **Answer**:  
   - Git triggers can automate deployment pipelines whenever changes are pushed to a specific branch (e.g., `master`).
   - Use CI/CD tools like Jenkins or GitLab CI to automate the process.
   - Include scripts in the pipeline to deploy to staging or production environments when commits are merged.

## 8. **What are the best practices for commit messages in a team-based environment?**
   **Answer**:  
   - Write clear, concise commit messages explaining **why** the change was made, not just **what**.
   - Use conventional commit formats (e.g., `feat: add login`, `fix: resolve X bug`).
   - Limit subject lines to 50 characters, and provide detailed descriptions if necessary.

## 9. **How do you ensure the security of sensitive data in a Git repository?**
   **Answer**:  
   - Use **Git hooks** to prevent accidental commits of sensitive data.
   - Add sensitive files (e.g., `.env`, API keys) to `.gitignore`.
   - Use **Git Secrets** or **Talisman** to scan commits for sensitive data before pushing.

## 10. **What is the difference between `git pull --rebase` and `git pull`?**
   **Answer**:  
   - `git pull` fetches changes from the remote and **merges** them into your local branch, which can create a merge commit.
   - `git pull --rebase` fetches changes from the remote and **rebases** your local commits onto the latest remote changes, keeping the commit history linear.

## 11. **How do you ensure that your Git history remains clean in a collaborative team environment?**
   **Answer**:  
   - Use `git rebase` to keep a linear history by rebasing feature branches before merging.
   - Regularly pull the latest changes from the remote repository to avoid conflicts.
   - Use **pull requests** and enforce code reviews to ensure that only well-tested code is merged.
   - Set up **branch protection rules** to ensure that the main branch remains stable.

## 12. **How would you use `git bisect` to find the commit that introduced a bug?**
   **Answer**:  
   - **`git bisect`** is a binary search tool that helps identify which commit introduced a bug.
   - Start by running `git bisect start`, mark the "bad" and "good" commits, and Git will guide you through testing intermediate commits.
   - Narrow down the commit causing the bug using a series of `git bisect` commands, and once found, use `git bisect reset` to return to the original state.

---

### 1. **`git restore --staged <file_name>`**
   - **Purpose**: This command is used to **unstage** a file, meaning it will remove the file from the staging area but leave the changes in your working directory. This is useful if you've added a file to the staging area (`git add`) but want to undo that action.
   - **Usage**:
     ```bash
     git restore --staged <file_name>
     ```
     - This command does **not delete the file** or revert its changes; it only removes it from the staging area, making it ready for the next commit.

### 2. **`git rm --cached <file_name>`**
   - **Purpose**: This command removes a file from the **Git repository** while keeping the file in your working directory. It's useful when you want to stop tracking a file that has already been added to version control (like `.env` files or other local configuration files).
   - **Usage**:
     ```bash
     git rm --cached <file_name>
     ```
     - After running this command, Git will no longer track the file, but the file will still exist on your local machine. You would typically add the file to `.gitignore` to prevent it from being tracked in the future.

---

### Key Differences:
- **`git restore --staged <file_name>`**: Removes the file from the staging area, but the file remains in the working directory with changes.
- **`git rm --cached <file_name>`**: Removes the file from Git's version control but leaves the file intact in the working directory.


