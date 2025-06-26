# Git pull vs Git clone

---

## 🔄 `git clone`

- **What it does:**
    
    Copies an entire remote repository **for the first time** to your local machine.
    
- **When to use it:**
    
    When you want to create a **new local copy** of a repository that you don’t have yet.
    
- **What happens:**
    - Downloads all files, branches, and commit history.
    - Sets up the remote named `origin` automatically.
    - Creates a local working copy ready for development.
- **Example:**
    
    ```bash
    git clone https://github.com/user/repo.git
    
    ```
    

---

## ⬇️ `git pull`

- **What it does:**
    
    Updates your existing local repository by **fetching changes from the remote** and merging them into your current branch.
    
- **When to use it:**
    
    After you have cloned a repo, use `git pull` regularly to get the latest changes others have pushed.
    
- **What happens:**
    - Downloads new commits from the remote branch you track.
    - Merges those changes into your current local branch (or rebases if configured).
- **Example:**
    
    ```bash
    git pull origin main
    
    ```
    

---

## Summary

| Command | Purpose | Use Case |
| --- | --- | --- |
| `git clone` | Create a new local copy of a repo | First time you get the repo |
| `git pull` | Update existing local repo with remote changes | Keep your local repo up-to-date |

---