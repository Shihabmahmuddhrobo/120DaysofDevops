# Git Snapshot

A **Git snapshot** refers to the state of your entire project (all tracked files) at a particular point in time. In Git, every **commit** you make is essentially a **snapshot** of your codebase. Here's a clearer breakdown:

---

### 🔍 What Is a Git Snapshot?

- A **snapshot** in Git is a complete recording of the **state of all tracked files** in your repository at the moment of a **commit**.
- It’s not just a difference (like in traditional version control systems like SVN), but a **full snapshot** of your files (internally optimized using pointers for unchanged files).

---

### 🧠 Key Concepts

| Concept | Description |
| --- | --- |
| **Commit** | A snapshot of your project. It stores the content of all tracked files. |
| **Staging area** | You build the snapshot in the staging area before committing. |
| **Blob (Binary Large Object)** | Git stores file contents as blobs. If a file hasn’t changed, Git reuses the blob from previous snapshots. |

---

### 🧱 How It Works Internally

1. When you run `git add`, Git stages changes and prepares the **next snapshot**.
2. When you run `git commit`, Git:
    - Captures a snapshot of all the staged files.
    - Stores this snapshot (a tree of blobs) with a commit message and metadata (author, timestamp, etc.).
3. Git optimizes storage by **reusing unchanged blobs** (files that didn’t change).

---

### 📌 Example

```bash
git add .
git commit -m "Snapshot of project after adding login feature"

```

At this point, Git saves a snapshot of all tracked files in the current state.

---

### 🧪 Summary

- Git is **snapshot-based**, not difference-based.
- Each commit = a **snapshot of your project** at that time.
- Efficient storage ensures only **changed files** are saved as new blobs.