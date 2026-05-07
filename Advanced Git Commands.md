# 🚀 Advanced Git & GitHub Commands Cheat Sheet

---

# 📚 Table of Contents

- 🧠 Advanced Commit Operations  
- 🌿 Advanced Branching  
- 🔀 Advanced Merge & Rebase  
- 🧹 History Rewriting  
- 🔍 Advanced Inspection  
- 🚀 Remote Advanced Commands  
- 🏷️ Tags & Releases  
- 🧰 Debugging Tools  

---

# 🧠 Advanced Commit Operations

## ✏️ Amend Last Commit

```bash
git commit --amend -m "Updated commit message"
```

### 📌 What it does
Modifies the most recent commit (message or content) without creating a new commit.

---

## 📦 Add files to last commit

```bash
git add .
git commit --amend --no-edit
```

### 📌 What it does
Adds new changes to the previous commit without changing its message.

---

## ⏪ Undo last commit (keep changes)

```bash
git reset --soft HEAD~1
```

### 📌 What it does
Removes the last commit but keeps your changes staged.

---

## ❌ Undo last commit (remove changes)

```bash
git reset --hard HEAD~1
```

### 📌 What it does
Completely deletes the last commit and all its changes.

---

# 🌿 Advanced Branching

## 🌱 Create & switch branch

```bash
git checkout -b feature-dashboard
```

### 📌 What it does
Creates a new branch and immediately switches to it.

---

## 🔀 Rename branch

```bash
git branch -m new-branch-name
```

### 📌 What it does
Renames the current branch.

---

## 🧹 Delete remote branch

```bash
git push origin --delete feature-login
```

### 📌 What it does
Removes a branch from GitHub (remote repository).

---

## 📡 Track remote branch

```bash
git branch --set-upstream-to=origin/main
```

### 📌 What it does
Links local branch to a remote branch for easy push/pull.

---

# 🔀 Advanced Merge & Rebase

## 🔗 Merge without fast-forward

```bash
git merge --no-ff feature-login
```

### 📌 What it does
Merges a branch while preserving full branch history.

---

## 🔄 Rebase branch

```bash
git rebase main
```

### 📌 What it does
Rewrites commit history to apply changes on top of another branch.

---

## 🚨 Abort merge

```bash
git merge --abort
```

### 📌 What it does
Cancels a merge operation and restores previous state.

---

## 🚨 Abort rebase

```bash
git rebase --abort
```

### 📌 What it does
Stops an ongoing rebase and returns to original state.

---

## 🧹 Interactive rebase

```bash
git rebase -i HEAD~3
```

### 📌 What it does
Lets you edit, reorder, or delete last 3 commits.

---

# 🧹 History Rewriting

## ✏️ Edit commit history

```bash
git rebase -i HEAD~5
```

### 📌 What it does
Allows modifying last 5 commits (squash, edit, delete).

---

## 🧼 Remove file from entire history

```bash
git filter-branch --tree-filter 'rm -f file.txt' HEAD
```

### 📌 What it does
Deletes a file from all commits in history.

---

## 🔥 Reset to remote state

```bash
git reset --hard origin/main
```

### 📌 What it does
Forces local branch to exactly match remote branch.

---

# 🔍 Advanced Inspection

## 📜 Commit graph view

```bash
git log --graph --oneline --all
```

### 📌 What it does
Shows visual tree of all branches and commits.

---

## 🕵️ Check file changes

```bash
git blame index.html
```

### 📌 What it does
Shows who changed each line of a file.

---

## 📊 Compare commits

```bash
git diff commit1 commit2
```

### 📌 What it does
Shows differences between two commits.

---

## 📦 File history

```bash
git log --follow index.html
```

### 📌 What it does
Tracks full history of a specific file.

---

# 🚀 Remote Advanced Commands

## 🔗 Add upstream remote

```bash
git remote add upstream https://github.com/other/repo.git
```

### 📌 What it does
Connects your repo to original repository (fork setup).

---

## 📡 Fetch all remotes

```bash
git fetch --all
```

### 📌 What it does
Downloads updates from all remote repositories.

---

## 🔄 Sync fork

```bash
git fetch upstream
git merge upstream/main
```

### 📌 What it does
Updates your fork with latest changes from original repo.

---

## 🚀 Force push (danger)

```bash
git push --force
```

### 📌 What it does
Overwrites remote history with local history.

---

## 🚀 Safer force push

```bash
git push --force-with-lease
```

### 📌 What it does
Force pushes only if remote hasn't changed unexpectedly.

---

# 🏷️ Tags & Releases

## 🏷️ Create tag

```bash
git tag -a v1.0 -m "Release version 1.0"
```

### 📌 What it does
Creates a labeled snapshot of project (release version).

---

## 🚀 Push tag

```bash
git push origin v1.0
```

### 📌 What it does
Uploads a specific version tag to GitHub.

---

## 🧹 Delete local tag

```bash
git tag -d v1.0
```

### 📌 What it does
Removes tag from local repository.

---

## ☁️ Delete remote tag

```bash
git push origin --delete v1.0
```

### 📌 What it does
Deletes tag from GitHub repository.

---

# 🧰 Debugging Tools

## 🧪 Start bisect

```bash
git bisect start
```

### 📌 What it does
Helps find which commit introduced a bug.

---

## ✅ Mark good commit

```bash
git bisect good
```

### 📌 What it does
Marks a working commit during debugging.

---

## ❌ Mark bad commit

```bash
git bisect bad
```

### 📌 What it does
Marks a broken commit during debugging.

---

## 📦 Show stash changes

```bash
git stash show -p
```

### 📌 What it does
Displays detailed changes saved in stash.

---

## 🧹 Clean untracked files

```bash
git clean -f
```

### 📌 What it does
Removes untracked files from working directory.

---

## 🧹 Clean directories

```bash
git clean -fd
```

### 📌 What it does
Removes untracked files and folders.

---

# 💡 Pro Tips

- ⚡ Use rebase for clean commit history  
- ⚡ Prefer `--force-with-lease` over `--force`  
- ⚡ Never rewrite shared public history  
- ⚡ Use `git log --graph` for visualization  
- ⚡ Always pull before pushing in team projects  

---

# 🎯 End of Advanced Git Guide

Master these commands to work like a professional developer 🚀
