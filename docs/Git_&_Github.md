# Git & GitHub – Quick Setup Guide

A quick reference for maintaining your DSA practice solutions on GitHub.


> Git is the version control system; GitHub is the platform where you host and share repositories. You may need to authenticate with GitHub when pushing for the first time.


## 1. Create a Repository on GitHub

1. Log in to [GitHub](https://github.com/).
2. Click the **New Repository** option.
3. Give your repository a name (e.g., `DSA-Practice`).
4. Choose Public or Private.
5. Create the repository. For this workflow, leave it empty (don't initialise with a README).

## 2. Initialise Git Locally

Open your DSA folder in VS Code and launch the integrated terminal.

Configure your Git identity (only needed once):

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Initialise the repository:

```bash
git init
```

## 3. Connect Your Local Repository to GitHub

Copy the HTTPS URL of your newly created GitHub repository.

```bash
git remote add origin <repository-url>
git branch -M main
```

## 4. Push Your First Commit

```bash
git add .
git commit -m "Initial commit"
git push -u origin main
```

Your local files should now be available in your GitHub repository!

## 5. Subsequent Updates

Whenever you add or modify your DSA solutions:

```bash
git add .
git commit -m "Add array problems"
git push
```

## 6. Useful Git Commands

| Command | Purpose |
|---|---|
| `git status` | Check modified and untracked files |
| `git add .` | Stage changes |
| `git commit -m "message"` | Save a commit |
| `git log` | View commit history |
| `git remote -v` | View connected remotes |
| `git pull` | Fetch and integrate remote changes |
| `git push` | Upload commits to GitHub |