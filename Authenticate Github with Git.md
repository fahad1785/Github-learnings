# 🔐 GitHub Authentication Guide (HTTPS + SSH + CLI)

---

# 📚 Table of Contents

- [🔐 HTTPS + Personal Access Token (PAT)](#-https--personal-access-token-pat)
- [🔑 SSH Authentication](#-ssh-authentication)
- [⚡ GitHub CLI Authentication](#-github-cli-authentication)
- [🆚 Comparison](#-comparison)
- [🚨 Common Errors](#-common-errors)

---

# 🔐 HTTPS + Personal Access Token (PAT)

## 🎯 Scenario
You want to push code to GitHub using HTTPS.

## 🧩 Step 1: Generate Token

Create a token from:

https://github.com/settings/tokens

- Go to **Developer Settings**
- Select **Personal Access Tokens**
- Generate new token
- Copy it safely

---

## 🧩 Step 2: Use Token in Git

When Git asks for login:

```bash
Username: your_github_username
Password: your_personal_access_token
```

---

## 🚀 Example Push Flow

```bash
git add .
git commit -m "update code"
git push origin main
```

---

# 🔑 SSH Authentication

## 🎯 Scenario
You want password-less secure Git access.

---

## 🧩 Step 1: Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

---

## 🧩 Step 2: Start SSH Agent

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

## 🧩 Step 3: Copy SSH Key

```bash
cat ~/.ssh/id_ed25519.pub
```

---

## 🧩 Step 4: Add Key to GitHub

https://github.com/settings/keys

- Click **New SSH Key**
- Paste key
- Save

---

## 🧩 Step 5: Clone Repo Using SSH

```bash
git clone git@github.com:user/repo.git
```

---

## 🧪 Test Connection

```bash
ssh -T git@github.com
```

Expected output:

```text
Hi username! You've successfully authenticated.
```

---

# ⚡ GitHub CLI Authentication

## 🎯 Scenario
You want easiest login and GitHub automation.

---

## 🧩 Login

```bash
gh auth login
```

Choose:
- GitHub.com
- HTTPS or SSH
- Browser login

---

## 🧩 Check Status

```bash
gh auth status
```

---

## 🧩 Logout

```bash
gh auth logout
```

---

# 🆚 Comparison

| Method | Security | Ease | Best For |
|--------|----------|------|----------|
| HTTPS + PAT | Medium | Easy | Beginners |
| SSH | High | Medium | Developers |
| GitHub CLI | High | Very Easy | Automation |

---

# 🚨 Common Errors

## ❌ Authentication Failed

### Fix
- Check token permissions
- Regenerate token if expired
- Ensure correct username

---

## ❌ Permission Denied (SSH)

### Fix

```bash
ssh-add ~/.ssh/id_ed25519
```

---

# 🚀 Recommended Setup

- Use SSH for Git operations
- Use GitHub CLI for PRs and issues
- Use PAT only as backup

---

# 🎯 End of Guide
Master GitHub authentication for smooth development workflow.
