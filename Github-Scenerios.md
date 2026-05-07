# 🚀 Git & GitHub Scenario-Based Commands Cheat Sheet

---

# 📚 Table of Contents

- [🆕 Starting a New Project](#-starting-a-new-project)
- [📥 Cloning Existing Project](#-cloning-existing-project)
- [🌿 Working on a New Feature](#-working-on-a-new-feature)
- [☁️ Pushing Code to GitHub](#-pushing-code-to-github)
- [❌ Fixing Mistakes](#-fixing-mistakes)
- [💾 Saving Temporary Work](#-saving-temporary-work)
- [🔄 Updating Local Repository](#-updating-local-repository)
- [👨‍💻 Working with Teams](#-working-with-teams)
- [🚀 Release Management](#-release-management)
- [📜 Viewing History](#-viewing-history)
- [🔍 Comparing Changes](#-comparing-changes)
- [🧠 Daily Workflow](#-daily-workflow)

---

# 🆕 Starting a New Project

## 🎯 Scenario
You created a new project locally and want to start Git tracking.

---

## ⚙️ Initialize Repository

```bash
git init
```

💡 Creates a new Git repository.

---

## 📦 Check Status

```bash
git status
```

💡 Shows tracked/untracked files.

---

## ➕ Add Files

```bash
git add .
```

💡 Stages all files for commit.

---

## 💾 Commit First Version

```bash
git commit -m "Initial commit"
```

💡 Saves project snapshot.

---

# 📥 Cloning Existing Project

## 🎯 Scenario
You want to copy an existing GitHub project.

---

## 📌 Clone Repository

```bash
git clone https://github.com/user/project.git
```

💡 Downloads project locally.

---

## 📂 Enter Project Folder

```bash
cd project
```

---

# 🌿 Working on a New Feature

## 🎯 Scenario
You want to develop a feature without affecting main code.

---

## 🌱 Create & Switch Branch

```bash
git checkout -b feature-login
```

💡 Creates a new branch and switches to it.

---

## 📋 Check Branch

```bash
git branch
```

💡 Shows current branch.

---

## ➕ Add Changes

```bash
git add .
```

---

## 💾 Commit Feature

```bash
git commit -m "Added login feature"
```

---

# ☁️ Pushing Code to GitHub

## 🎯 Scenario
You want to upload your code to GitHub.

---

## 🔗 Add Remote Repo

```bash
git remote add origin https://github.com/user/project.git
```

---

## 🚀 Push First Time

```bash
git push -u origin main
```

---

## 🚀 Push Feature Branch

```bash
git push origin feature-login
```

---

# ❌ Fixing Mistakes

## 🎯 Scenario
You made unwanted changes.

---

## ↩️ Undo File Changes

```bash
git checkout -- app.js
```

💡 Restores last committed version.

---

## 📤 Unstage File

```bash
git reset app.js
```

---

## ⏪ Undo Last Commit

```bash
git reset --soft HEAD~1
```

💡 Keeps changes but removes commit.

---

## ⚠️ Hard Reset (Danger)

```bash
git reset --hard HEAD
```

💡 Deletes all local changes.

---

# 💾 Saving Temporary Work

## 🎯 Scenario
You need to switch branches but work is incomplete.

---

## 📦 Save Work

```bash
git stash
```

---

## 📋 View Stashes

```bash
git stash list
```

---

## ♻️ Restore Work

```bash
git stash pop
```

---

# 🔄 Updating Local Repository

## 🎯 Scenario
Team pushed new updates.

---

## 📥 Pull Latest Code

```bash
git pull origin main
```

---

## 📡 Fetch Updates Only

```bash
git fetch
```

---

# 👨‍💻 Working with Teams

## 🎯 Scenario
Merge feature into main branch.

---

## 🔀 Switch to Main

```bash
git checkout main
```

---

## 🔗 Merge Branch

```bash
git merge feature-login
```

---

## 🧹 Delete Branch

```bash
git branch -d feature-login
```

---

# 🚀 Release Management

## 🎯 Scenario
Releasing version 1.0

---

## 🏷️ Create Tag

```bash
git tag v1.0
```

---

## 🚀 Push Tags

```bash
git push origin --tags
```

---

# 📜 Viewing History

## 🎯 Scenario
Check previous commits.

---

## 📖 Full Log

```bash
git log
```

---

## ⚡ Compact Log

```bash
git log --oneline
```

---

# 🔍 Comparing Changes

## 🎯 Scenario
See differences before committing.

---

## 🔎 Check Changes

```bash
git diff
```

---

## 🔀 Compare Branches

```bash
git diff main feature-login
```

---

# 🧠 Daily Workflow

```bash
git pull origin main
git checkout -b new-feature
git add .
git commit -m "Added feature"
git push origin new-feature
```

---

# 💡 Pro Tips

- ✅ Always use branches for features  
- ✅ Pull before push  
- ✅ Write meaningful commit messages  
- ✅ Commit small changes frequently  
- ⚠️ Avoid pushing directly to main  
- 🔒 Keep main branch stable  

---

# 📖 Quick Reference Table

| Task | Command |
|------|--------|
| Initialize repo | `git init` |
| Clone repo | `git clone <url>` |
| Check status | `git status` |
| Create branch | `git checkout -b branch` |
| Switch branch | `git checkout branch` |
| Add files | `git add .` |
| Commit | `git commit -m ""` |
| Push | `git push origin main` |
| Pull | `git pull origin main` |
| Stash | `git stash` |

---

# 📚 Resources

- Git Documentation  
- GitHub Docs  
- Learn Git Branching  

this file looks great only keep the separating lines between each scenerio and remove other
