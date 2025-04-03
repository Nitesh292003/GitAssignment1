# GitAssignment1
Here is the structured breakdown of your Git operations:

---

### **Question 1: Initialize a Git Repository**

1. **Create a directory and initialize the repository:**
   ```bash
   mkdir GitAssignment1
   cd GitAssignment1
   git init
   ```
   - The output indicates that the repository is initialized with the default branch `master`.

2. **Create a file (`file1`) and commit the changes:**
   ```bash
   vi file1      # Create and edit the file
   git add file1
   git commit -m "hobbies added"
   ```
   - This adds and commits `file1` with the message "hobbies added".

---

### **Question 2: Create Feature Branches**

1. **List current branches and create a new branch (`branch1`):**
   ```bash
   git branch
   git branch branch1
   git branch  # Confirm the new branch
   ```

2. **Switch to `branch1`, create and commit `subject.txt`:**
   ```bash
   git checkout branch1
   vi subject.txt   # Add content to the file
   git add .
   git commit -m "subject is added"
   ```

3. **Switch back to `master` and create another branch (`branch2`):**
   ```bash
   git checkout master
   git checkout -b branch2
   ```

4. **Create and commit a new file (`sports`) on `branch2`:**
   ```bash
   vi sports   # Add content
   git add .
   git commit -m "sports added"
   ```

---

### **Question 3: Git Commands (Stash, Reset, Diff, Branch Management)**

1. **Modify the `sports` file and view the diff:**
   ```bash
   vi sports
   git diff
   ```
   - You edited the `sports` file, and the `git diff` command shows the changes (added `football`).

2. **Commit the changes:**
   ```bash
   git add .
   git commit -m "new sport added"
   ```

3. **Unstage changes with `git reset` and re-commit them:**
   ```bash
   git reset sports
   git status  # Verify the file is unstaged
   git add .
   git commit -m "rugby is added"
   ```

4. **Use `git stash` to save changes and pop them back:**
   ```bash
   git stash
   git checkout branch1
   git stash pop
   ```

5. **Update `subject.txt` and commit the changes on `branch1`:**
   ```bash
   vi subject.txt
   git add .
   git commit -m "subject is updated"
   ```

6. **Check the commit history using `git log`:**
   ```bash
   git log
   ```
   - This shows a list of commits, showing both `branch1` and `branch2`.

7. **Use `git reset` with `--soft` and `--hard`:**
   ```bash
   git reset --soft HEAD
   git log  # Check the commit history
   git reset --soft HEAD~  # Reset to the previous commit
   git log  # Check the updated history

   git reset --hard HEAD~  # Hard reset
   git log  # Check the history after hard reset
   ```

8. **Delete branches (`branch1` and `branch2`):**
   ```bash
   git branch -d branch2   # Delete a merged branch
   git branch -D branch1   # Force delete a branch
   ```

9. **Check the branch list after deletion:**
   ```bash
   git branch
   ```

---

### **Git Remote Operations and Push to GitHub**

1. **Add a remote repository and pull from it:**
   ```bash
   git remote add origin https://github.com/Nitesh292003/GitAssignment1.git
   git pull origin main   # Pull changes from the remote `main` branch
   ```
   - You encountered a warning about divergent branches and were prompted to specify how to reconcile them.

2. **Merge `branch2` into `master`:**
   ```bash
   git merge branch2
   ```
   - This fast-forwards the `master` branch to include the changes from `branch2`.

3. **Push changes to the remote `master` branch:**
   ```bash
   git push origin master
   ```
   - The changes are successfully pushed to the remote repository on GitHub.

---

