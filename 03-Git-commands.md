# 🚀 Git & GitHub Commands Cheat Sheet

A complete beginner-friendly Git and GitHub reference guide.

---

# 📚 Table of Contents

- [Git Setup](#-git-setup)
- [Repository Commands](#-repository-commands)
- [Branch Commands](#-branch-commands)
- [Remote Commands](#-remote-commands)
- [Undo Changes](#-undo-changes)
- [GitHub CLI](#-github-cli)
- [Workflow Example](#-workflow-example)

---

# ⚙️ Git Setup

## 🔹 Check Git Version

### Command

```bash
git --version
```

### Usage
Checks whether Git is installed and displays the current version.

### Example Output

```bash
git version 2.45.0
```

---

## 🔹 Configure Username

### Command

```bash
git config --global user.name "John Doe"
```

### Usage
Sets your Git username globally.

---

## 🔹 Configure Email

### Command

```bash
git config --global user.email "john@example.com"
```

### Usage
Sets your Git email globally.

---

# 📁 Repository Commands

## 🔹 Initialize Repository

### Command

```bash
git init
```

### Usage
Creates a new local Git repository.

---

## 🔹 Clone Repository

### Command

```bash
git clone https://github.com/user/repo.git
```

### Usage
Downloads an existing repository from GitHub.

---

# 🌿 Branch Commands

## 🔹 Create Branch

### Command

```bash
git branch feature-login
```

### Usage
Creates a new branch.

---

## 🔹 Switch Branch

### Command

```bash
git checkout feature-login
```

### Usage
Switches to another branch.

---

# 🌍 Remote Commands

## 🔹 Add Remote

### Command

```bash
git remote add origin https://github.com/user/repo.git
```

### Usage
Connects your local repository to GitHub.

---

## 🔹 Push Code

### Command

```bash
git push origin main
```

### Usage
Uploads code to GitHub.

---

# ↩️ Undo Changes

## 🔹 Remove From Staging

### Command

```bash
git reset app.py
```

### Usage
Unstages a file.

---

## 🔹 Hard Reset

⚠️ Warning: This deletes all local changes permanently.

### Command

```bash
git reset --hard HEAD
```

---

# 🐙 GitHub CLI

## 🔹 Login

### Command

```bash
gh auth login
```

### Usage
Authenticates GitHub CLI.

---

# 🔄 Workflow Example

```bash
git pull origin main
git checkout -b new-feature
git add .
git commit -m "Added feature"
git push origin new-feature
```

---

# 💡 Pro Tips

✅ Commit frequently  
✅ Use meaningful commit messages  
✅ Pull before pushing  
✅ Create branches for features  

---

# 📖 Helpful Resources

- Git Documentation
- GitHub Docs
- Learn Git Branching

---
