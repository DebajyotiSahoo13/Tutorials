# What is Git?

Git is a version control system (VCS).

- Tracks changes in files (usually code).
- Lets multiple people work on the same project without overwriting each other’s work.

Key features:
- History of changes
- Branching & merging
- Collaboration
- Works offline (local repository)

# What is GitHub?

GitHub is a web-based hosting platform for Git repositories.

Adds collaboration tools:
- Remote storage for your Git projects
- Pull Requests (PRs)
- Issues & discussions
- CI/CD workflows



Git = tool

GitHub = cloud platform built around Git

# Git Workflow Overview

- Working Directory → where you edit files.
- Staging Area → where you mark files to commit.
- Local Repository → where commits are stored.
- Remote Repository → copy hosted on GitHub.

```bash
Edit → git add → git commit → git push → GitHub
```

## First-Time Git Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list
```

## Starting a Project

```bash
# Initialize new local repository
git init

# Clone existing repository
git clone https://github.com/user/repo.git
```

# Basic Workflow

### Check Status
```bash
# Check repository status
git status

# Shows:
# - Modified files
# - Staged files
# - Untracked files
```

### Stage/Add Files
```bash
# Stage a specific file
git add filename.py

# Stage all changed files in current directory
git add .

# Stage all changed files everywhere
git add -A

# Stage only modified files (not new files)
git add -u

# Working Directory → Staging Area (Index)
#    (modified files)     (selected changes)

git restore --staged file_name 
# to unstage a file

```

### Committing Changes/Saving Files
https://github.com/conventional-changelog/commitlint?tab=readme-ov-file

- Permanently saving the staged changes to your local repository with a descriptive message.

```bash
# Commit staged changes with message
git commit -m "feat: add login validation"

# See what will be committed
git status

# View commit history
git log
```

- Staging (adding changes to a "holding area")

- Committing (permanently saving the staged changes)

### Pushing Changes

```bash
# Push current branch to its upstream branch
git push

# Push specific branch to remote
git push origin feature-login

# Push to different branch name
git push origin main:production

# Force push (use with caution!)
git push -f origin main

git push --force-with-lease
# safer than --force; prevents overwriting others' new work
```

## Branch Management

```bash
# List all local branches
git branch

# Create a new branch named "feature-login"
git branch feature-login

# Switch to the new feature branch
git checkout feature-login
git checkout -b new_branch

# Delete local branch
git branch -d old-feature

# Delete remote branch
git push origin --delete stale-branch
```

## Git Pull Operations

```bash
# Pull from current branch's upstream
git pull

# Pull from specific branch
git pull origin development

# Pull without auto-merge (fetch + manual merge)
git fetch origin
git merge origin/main

# Pull with rebase instead of merge
git pull --rebase origin main

# Fetch all branches from remote
git fetch --all
```

## Rewriting History & Amending Commits

```bash
# Amend last commit (change message/content)
git commit --amend -m "Improved login validation"

# Change multiple previous commits (interactive rebase)
git rebase -i HEAD~3
# Then choose "reword" or "edit" for commits

# Add changes to last commit without changing message
git add .
git commit --amend --no-edit
```

## Git Stash

```bash
# Stash changes temporarily
git stash

# Stash with message
git stash push -m "Work in progress"

# List all stashes
git stash list

# Apply last stash and keep it in stack
git stash apply

# Apply specific stash
git stash apply stash@{1}

# Apply and remove from stash stack
git stash pop
```

## Git Rebase

```bash
# Rebase current branch onto main
git rebase main

# Interactive rebase (last 4 commits)
git rebase -i HEAD~4

# Continue after resolving conflicts
git rebase --continue

# Abort rebase operation
git rebase --abort
```