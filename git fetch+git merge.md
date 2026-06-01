# Git Fetch

`git fetch` downloads new commits, branches, and tags from a remote repository **without modifying your current working branch**.

## Basic Usage

```bash
git fetch
```

## Fetch from a Specific Remote

```bash
git fetch origin
```

## Fetch All Remotes

```bash
git fetch --all
```

## See What Changed After Fetching

### See Commits That Exist on the Remote but Not Locally

If you're on the `main` branch:

```bash
git log HEAD..origin/main --oneline
```

This shows commits that were fetched and are present on `origin/main` but not on your local `main` branch.

### See a Summary of Changed Files

```bash
git diff --stat HEAD origin/main
```

Example output:

```text
src/app.js     | 12 +++++++-----
README.md      |  5 +++--
2 files changed, 10 insertions(+), 7 deletions(-)
```

### See the Actual Code Differences

```bash
git diff HEAD origin/main
```

### See Which Branches Have New Commits

```bash
git branch -vv
```

Example output:

```text
* main abc1234 [origin/main: behind 3] Current work
```

This indicates that your local branch is 3 commits behind the remote branch.

### Compare Local and Remote Branch Histories

```bash
git log --oneline --graph --decorate HEAD...origin/main
```

This displays commits that differ between your local and remote branches.

### Quick Overview

```bash
git status
```

After a fetch, you may see something like:

```text
Your branch is behind 'origin/main' by 3 commits.
```

## If You're Not on `main`

Replace `main` with your branch name:

```bash
git diff HEAD origin/feature-branch
git log HEAD..origin/feature-branch --oneline
```

## Common Workflow

```bash
git fetch
git log --oneline HEAD..@{upstream}
git diff --stat HEAD @{upstream}
```

`@{upstream}` automatically refers to the remote-tracking branch that your current branch follows.

## Update Your Local Branch

Merge the fetched changes:

```bash
git merge origin/main
```

Or rebase your branch:

```bash
git rebase origin/main
```

## Alternative: Use `git pull`

If you want to fetch and update your branch in a single command:

```bash
git pull
```

This is essentially equivalent to:

```bash
git fetch
git merge
```
