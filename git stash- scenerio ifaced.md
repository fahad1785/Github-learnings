# Scenerio

## I created two files in main branch which i wanted to create in May16 branch now what can i do

---

````md
# Moving Files from `main` Branch to `May16` Branch

If you created two files in the `main` branch but actually wanted them in the `May16` branch, you can move them safely.

---

# Case 1 — Files are NOT committed yet

If the files are only created locally and not committed:

## Step 1: Check Git Status
```bash
git status
````

## Step 2: Stash the Changes

```bash
git stash
```

## Step 3: Switch to `May16` Branch

```bash
git checkout May16
```

## Step 4: Apply the Stashed Changes

```bash
git stash pop
```

Now commit the files in the `May16` branch.

---

# Case 2 — Files are already committed in `main`

If you already committed them in `main`, follow these steps.

## Step 1: Get the Commit Hash

```bash
git log --oneline
```

Example:

```bash
a1b2c3 Added two files
```

## Step 2: Switch to `May16`

```bash
git checkout May16
```

## Step 3: Cherry-pick the Commit

```bash
git cherry-pick a1b2c3
```

This copies the commit from `main` into `May16`.

---

# Step 4 (Optional) Remove Commit from `main`

If you do NOT want those files in `main`:

## If the Commit is NOT pushed

```bash
git checkout main
git reset --hard HEAD~1
```

## If the Commit is already pushed

Use `revert` instead:

```bash
git checkout main
git revert a1b2c3
```

This safely removes the changes by creating a reverse commit.

---

# Quick Recommendation

* **Not committed** → Use `git stash`
* **Committed** → Use `git cherry-pick`
* **Already pushed** → Use `git revert` instead of `git reset`

```
```
