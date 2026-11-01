
# 📚 Git Cheat Sheet

## ⚙️ Git Configuration

Configure your username and email address. Git uses these details to identify the author of each commit.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

**Verify your configuration:**

```bash
git config --global --list
```

## 🚀 Initialization & Git Status

| Command | Description |
|---|---|
| `git --version` | Displays the installed Git version |
| `git init` | Initializes a Git repository |
| `git init -b main` | Initializes a repository with `main` as the initial branch |
| `git status` | Displays the current repository status |
| `git config --global --list` | Displays global Git configuration |
| `git rev-parse --show-toplevel` | Displays the root directory of the repository |

---


## 📦 Staging Changes

### ➕ Add files to the staging area

```bash
# Stage a specific file
git add filename

# Stage multiple files
git add file1 file2

# Stage all changes in the current directory
git add .

# Stage all changes across the repository
git add -A
```

### 🔍 Check staging status

```bash
# Check staged and unstaged changes
git status

# Display unstaged changes
git diff

# Display staged changes
git diff --staged
```

### ↩️ Unstage files

```bash
# Unstage a specific file without deleting its changes
git restore --staged filename

# Unstage all staged files
git restore --staged .
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git add filename` | Stages a specific file |
| `git add .` | Stages changes under the current directory |
| `git add -A` | Stages all changes across the repository |
| `git status` | Shows staged and unstaged changes |
| `git diff` | Shows unstaged changes |
| `git diff --staged` | Shows staged changes |
| `git restore --staged filename` | Unstages a specific file |

---


## 💾 Committing Changes


### 📝 Create a Commit

```bash
# Commit staged changes with a message
git commit -m "Add initial project files"

# Stage all tracked modified and deleted files, then commit
git commit -am "Update project files"

# Open the default editor to write a commit message
git commit
```

**Note:** `git commit -am` does not include newly created, untracked files. You must stage new files using `git add` first.

### ✏️ Modify the Last Commit

```bash
# Change the last commit message
git commit --amend -m "Updated commit message"

# Add staged changes to the previous commit
git commit --amend --no-edit
```

**Note:** Avoid amending commits that have already been shared with others, as it changes commit history.

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git commit -m "message"` | Creates a commit with a message |
| `git commit -am "message"` | Commits tracked modified and deleted files |
| `git commit` | Opens the editor to write a commit message |
| `git commit --amend -m "message"` | Changes the previous commit message |
| `git commit --amend --no-edit` | Adds staged changes to the previous commit without changing its message |
| `git log` | Displays commit history |
| `git show` | Displays details of the latest commit |

---


## 🌿 Branching

### 🌱 Create and View Branches

```bash
# List all local branches
git branch

# Create a new branch
git branch feature-login

# Create a branch and switch to it
git checkout -b feature-login

# Create and switch to a branch (modern command)
git switch -c feature-login
```

### 🔄 Switch Between Branches

```bash
# Switch to an existing branch
git switch main

# Switch using the older command
git checkout main

# Switch to the previously checked-out branch
git switch -
git checkout -
```

### ✏️ Rename and Delete Branches

```bash
# Rename the current branch
git branch -m new-branch-name

# Delete a merged branch
git branch -d feature-login

# Force delete a branch
git branch -D feature-login
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git branch` | Lists local branches |
| `git branch branch-name` | Creates a new branch |
| `git checkout -b branch-name` | Creates and switches to a new branch |
| `git switch -c branch-name` | Creates and switches to a new branch |
| `git switch branch-name` | Switches to an existing branch |
| `git branch -m new-name` | Renames the current branch |
| `git branch -d branch-name` | Deletes a merged branch |
| `git branch -D branch-name` | Force deletes a branch |
| `git branch -a` | Lists local and remote-tracking branches |

---


## 🔀 Merging


### 🔄 Merge a Branch

```bash
# Switch to the branch where changes should be merged
git switch main

# Merge feature-login into the current branch
git merge feature-login
```

**Note:** The branch you are currently on is the target branch. The branch specified in `git merge` is the source branch.


### ↩️ Abort a Merge

```bash
# Cancel the current merge and return to the pre-merge state
git merge --abort
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git merge branch-name` | Merges the specified branch into the current branch |
| `git merge --no-ff branch-name` | Creates a merge commit even when fast-forward is possible |
| `git merge --abort` | Aborts an ongoing merge |

---


## ☁️ Synchronizing with GitHub


### 🔗 Connect Local Repository to GitHub

```bash
# Add a remote repository
git remote add origin https://github.com/username/repository.git

# View configured remote repositories
git remote -v

# Change the remote repository URL
git remote set-url origin https://github.com/username/repository.git
```

### ⬆️ Push Changes to GitHub

```bash
# Push the current branch to GitHub
git push origin main

# Push and set upstream tracking
git push -u origin main

# Push the current branch to its configured upstream
git push
```

### ⬇️ Pull Changes from GitHub

```bash
# Fetch and merge changes from the remote main branch
git pull origin main

# Pull changes from the configured upstream branch
git pull
```

### 📥 Fetch Changes from GitHub

```bash
# Fetch changes from the remote repository
git fetch origin

```

**Note:** `git fetch` downloads remote changes but does not automatically merge them into your current local branch. `git pull` fetches and integrates remote changes.

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git remote -v` | Lists configured remote repositories |
| `git remote add origin URL` | Adds a remote repository |
| `git remote set-url origin URL` | Updates the remote repository URL |
| `git push origin main` | Pushes the local main branch to origin |
| `git push -u origin main` | Pushes and sets upstream tracking |
| `git pull origin main` | Fetches and integrates changes from origin/main |
| `git fetch origin` | Downloads changes from origin without merging |


### 🔄 Clone a Repository

```bash
# Clone a remote repository
git clone https://github.com/username/repository.git

# Clone into a directory with a custom name
git clone https://github.com/username/repository.git my-project
```

---


## 📜 Git History


### 📋 View Commit History

```bash
# Display complete commit history
git log

# Display commit history in one line per commit
git log --oneline

# Display the latest 5 commits
git log -5

# Display history with branch graph
git log --oneline --graph --all

```

### 🔍 Inspect a Commit

```bash
# Display details of the latest commit
git show

# Display details of a specific commit
git show commit-hash

# Display files changed in a commit
git show --stat commit-hash
```

### 📂 View File History

```bash
# Display commits that modified a specific file
git log -- filename

# Display changes made to a specific file
git log -p -- filename

```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git log` | Displays commit history |
| `git log --oneline` | Displays compact commit history |
| `git log --graph --all` | Displays commit history as a graph |
| `git show` | Displays details of a commit |
| `git show --stat` | Displays files changed in a commit |
| `git log -- filename` | Displays the history of a file |
| `git log -p -- filename` | Displays changes made to a file across commits |


---


## ↩️ Undoing Changes


### 📦 Unstage Changes

```bash
# Unstage a specific file
git restore --staged filename

# Unstage all staged files
git restore --staged .
```

### 📝 Discard Working Directory Changes

```bash
# Discard changes in a specific file
git restore filename

# Discard all unstaged changes
git restore .
```

**Warning:** These commands permanently discard the specified uncommitted changes.

### ⏪ Reset Commits

```bash
# Move HEAD to the previous commit and keep changes staged
git reset --soft HEAD~1

# Move HEAD to the previous commit and keep changes unstaged
git reset --mixed HEAD~1

# Move HEAD to the previous commit and discard changes
git reset --hard HEAD~1
```

### ↩️ Revert a Commit

```bash
# Create a new commit that reverses a specific commit
git revert commit-hash

# Revert the latest commit
git revert HEAD
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git restore --staged filename` | Unstages a file |
| `git restore filename` | Discards unstaged changes in a file |
| `git reset --soft HEAD~1` | Undoes the latest commit but keeps changes staged |
| `git reset --mixed HEAD~1` | Undoes the latest commit but keeps changes unstaged |
| `git reset --hard HEAD~1` | Undoes the latest commit and discards its changes |
| `git revert commit-hash` | Creates a new commit to reverse an earlier commit |

---



## 📦 Git Stash

Git stash temporarily saves uncommitted changes.

### 💾 Save Changes

```bash
# Stash tracked changes
git stash

# Stash changes with a description
git stash save "Work in progress"

# Include untracked files
git stash -u

```

### 📋 View Stashes

```bash
# List all stashes
git stash list

# Display the latest stash
git stash show

# Display the latest stash with detailed changes
git stash show -p
```

### ♻️ Restore Stashed Changes

```bash
# Restore the latest stash and keep it in the stash list
git stash apply

# Restore a specific stash
git stash apply stash@{1}

# Restore and remove the latest stash
git stash pop
```

### 🗑️ Remove Stashes

```bash
# Delete a specific stash
git stash drop stash@{0}

# Delete all stashes
git stash clear
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `git stash` | Temporarily saves tracked changes |
| `git stash -u` | Includes untracked files |
| `git stash -a` | Includes ignored files too |
| `git stash list` | Lists all stashes |
| `git stash show -p` | Displays detailed stash changes |
| `git stash apply` | Restores changes without deleting the stash |
| `git stash pop` | Restores changes and removes the stash |
| `git stash drop` | Deletes a specific stash |
| `git stash clear` | Deletes all stashes |

---






