# Git Learning Session: Beginner to Advanced

## Beginner Level: Understanding Git and Basic Commands

### Topic: Setting Up Git and Basic Operations

#### Explanation
Git is a version control system that helps developers track and manage changes in their codebase. At the beginner level, it's important to understand:
- Initializing a repository
- Adding and committing files
- Checking the status of the repository
- Viewing commit history

#### Example Commands
```bash
# Step 1: Configure Git (only needed once)
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

# Step 2: Initialize a repository
git init my_project
cd my_project

# Step 3: Create a file and add it to Git
echo "Hello Git" > file.txt
git add file.txt

# Step 4: Commit the changes
git commit -m "Initial commit with file.txt"

# Step 5: Check repository status
git status

# Step 6: View commit history
git log --oneline
```

🔹 **Key Takeaways:** You now understand how to set up Git, track changes, and commit files.

---

## Intermediate Level: Working with Branches and Merging

### Topic: Branching and Merging Strategies

#### Explanation
Branches in Git allow developers to work on new features or bug fixes without affecting the main codebase. Understanding how to create, switch, merge, and resolve conflicts is crucial at this stage.

#### Example Commands
```bash
# Step 1: Create and switch to a new branch
git checkout -b feature-branch

# Step 2: Make changes and commit
echo "New feature" > feature.txt
git add feature.txt
git commit -m "Added new feature"

# Step 3: Switch back to main branch
git checkout main

# Step 4: Merge the feature branch into main
git merge feature-branch
```

**Handling Merge Conflicts:**  
If two branches modify the same line in a file, a merge conflict occurs. You must manually resolve it in the affected file and then run:
```bash
git add resolved_file.txt
git commit -m "Resolved merge conflict"
```

🔹 **Key Takeaways:** You now know how to create and merge branches, and resolve conflicts when they arise.

---

## Advanced Level: Git Rebase, Cherry-Pick, and Stashing

### Topic: Rewriting Git History with Rebase

#### Explanation
Rebasing allows you to clean up commits by moving or modifying them. It’s useful when keeping a clean commit history or integrating feature branches with the main branch.

#### Example Commands
```bash
# Step 1: Check commit history
git log --oneline

# Step 2: Start interactive rebase (modify last 3 commits)
git rebase -i HEAD~3
```
You'll see something like this in an editor:
```
pick a1b2c3 First commit
pick d4e5f6 Second commit
pick g7h8i9 Third commit
```
Change `pick` to:
```
reword a1b2c3 First commit (modify the message)
squash d4e5f6 Second commit (merge into previous commit)
pick g7h8i9 Third commit
```
After saving, Git will ask for a new commit message.

#### Force Push After Rewriting History
```bash
git push origin main --force
```

### Topic: Cherry-Picking Commits

#### Explanation
Cherry-picking allows you to apply a specific commit from one branch into another without merging the entire branch.

#### Example Commands
```bash
# Step 1: Identify the commit hash
git log --oneline

# Step 2: Cherry-pick the desired commit
git cherry-pick <commit-hash>
```

### Topic: Stashing Changes

#### Explanation
Stashing allows you to save changes temporarily without committing them. This is useful when switching branches without losing changes.

#### Example Commands
```bash
# Step 1: Stash uncommitted changes
git stash

# Step 2: View stash list
git stash list

# Step 3: Apply the latest stash
git stash apply

# Step 4: Drop a stash after applying
git stash drop
```

🔹 **Key Takeaways:** You now know how to rewrite commit history using rebase, apply specific commits with cherry-pick, and stash changes for later use.

---

## Conclusion
- **Beginner:** Set up Git, track files, and commit changes.
- **Intermediate:** Use branching, merging, and resolve conflicts.
- **Advanced:** Rebase commits for a cleaner history, cherry-pick commits, and stash changes temporarily.

Would you like a hands-on activity for each level? 🚀
