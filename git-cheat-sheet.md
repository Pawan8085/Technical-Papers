
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

Staging is the process of selecting changes that you want to include in your next commit.

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

A commit is a snapshot of the staged changes in your repository. Each commit has a unique ID (hash), author, timestamp, and commit message.

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

