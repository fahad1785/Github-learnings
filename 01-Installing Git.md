# 🧰 Installing Git on Windows, Linux & macOS

---

# 🪟 Windows Installation

## 🎯 Method 1: Official Installer (Recommended)

### 🔗 Download Git
https://git-scm.com/download/win

---

## 🧩 Steps

1. Download the installer  
2. Run the `.exe` file  
3. Keep default options (recommended)  
4. Click Next → Next → Install  
5. Finish setup  

---

## ✅ Verify Installation

```bash
git --version
```

### 📌 Expected Output
```bash
git version 2.xx.x
```

---

## 💡 Bonus Tools Installed

- Git Bash (Linux-like terminal)
- Git GUI
- SSH support

---

# 🐧 Linux Installation

## 🎯 Ubuntu / Debian

```bash
sudo apt update
sudo apt install git -y
```

---

## 🎯 Fedora

```bash
sudo dnf install git -y
```

---

## 🎯 Arch Linux

```bash
sudo pacman -S git
```

---

## ✅ Verify Installation

```bash
git --version
```

---

## 💡 Optional Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

# 🍎 macOS Installation

## 🎯 Method 1: Homebrew (Best)

```bash
brew install git
```

https://brew.sh

---

## 🎯 Method 2: Xcode Command Line Tools

```bash
git --version
```

If not installed, macOS will prompt installation automatically.

---

## 🎯 Method 3: Official Installer

https://git-scm.com/download/mac

---

## ✅ Verify Installation

```bash
git --version
```

---

# 🔐 Final Setup (All OS)

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

# 🧠 Quick Summary

| OS | Method |
|----|--------|
| 🪟 Windows | Git installer (.exe) |
| 🐧 Linux | apt / dnf / pacman |
| 🍎 macOS | brew / Xcode tools |

---

# 🚀 Pro Tip

```bash
git init
git status
```

If both work → Git is installed correctly 🎉
