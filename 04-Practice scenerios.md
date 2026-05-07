# 🧪 Git Practice Scenarios (Beginner to Intermediate)

---

# 🆕 Scenario 1: Start a New Project

## 🎯 Task
Create a new project from scratch and initialize Git.

## 🧩 Steps
```bash
mkdir my-website
cd my-website
git init
touch index.html
git add .
git commit -m "Initial website setup"
```

---

# 📥 Scenario 2: Clone Existing Project

## 🎯 Task
Download an existing GitHub project and explore it.

## 🧩 Steps
```bash
git clone https://github.com/user/project.git
cd project
git status
```

---

# 🌿 Scenario 3: Create Feature Branch

## 🎯 Task
Work on a login feature without affecting main code.

## 🧩 Steps
```bash
git checkout -b feature-login
touch login.html
git add .
git commit -m "Added login page"
```

---

# ☁️ Scenario 4: Push Code to GitHub

## 🎯 Task
Upload your local project to GitHub.

## 🧩 Steps
```bash
git remote add origin https://github.com/user/project.git
git push -u origin main
```

Or feature branch:
```bash
git push origin feature-login
```

---

# 🔄 Scenario 5: Sync Latest Changes

## 🎯 Task
Team updated code, you need latest version.

## 🧩 Steps
```bash
git pull origin main
```

---

# ❌ Scenario 6: Undo File Changes

## 🎯 Task
You broke a file and want to restore it.

## 🧩 Steps
```bash
git checkout -- index.html
```

---

# 📤 Scenario 7: Unstage File

## 🎯 Task
You added a file by mistake.

## 🧩 Steps
```bash
git reset index.html
```

---

# 💾 Scenario 8: Temporary Save Work

## 🎯 Task
Switch branch without losing progress.

## 🧩 Steps
```bash
git stash
git checkout main
git stash pop
```

---

# 🔀 Scenario 9: Merge Feature Branch

## 🎯 Task
Combine feature into main branch.

## 🧩 Steps
```bash
git checkout main
git merge feature-login
```

---

# 🏷️ Scenario 10: Release Version

## 🎯 Task
Mark a release version.

## 🧩 Steps
```bash
git tag v1.0
git push origin --tags
```

---

# 📜 Scenario 11: View Commit History

## 🎯 Task
Check past commits.

## 🧩 Steps
```bash
git log --oneline
```

---

# 🔍 Scenario 12: Compare Changes

## 🎯 Task
See differences in code.

## 🧩 Steps
```bash
git diff
git diff main feature-login
```

---

# 🧠 Bonus Workflow (Real Project Flow)

```bash
git init
touch app.js
git add .
git commit -m "start project"

git checkout -b feature-ui
# make changes
git add .
git commit -m "UI added"

git checkout main
git merge feature-ui

git push origin main
```

---

# 🚀 End of Practice Set

Practice these scenarios repeatedly to master Git workflows.
