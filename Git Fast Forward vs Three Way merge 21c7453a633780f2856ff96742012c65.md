# Git Fast Forward vs Three Way merge

---

### 🔁 1. Fast-Forward Merge

### ✅ Definition:

A **fast-forward merge** happens when the branch you're merging **has not diverged** from the target branch. In this case, Git simply moves the pointer of the target branch **forward to the latest commit** of the source branch — no merge commit is created.

### 🧠 Requirements:

- The target branch is **a direct ancestor** of the source branch.
- No new commits exist on the target branch since the branch-off.

### 📘 Example:

```bash
# Start on main branch
git checkout main
# Merge feature (which is ahead of main)
git merge feature

```

If `main` has not changed since `feature` branched off, this results in a fast-forward.

### 📈 Visual:

```
main:    A---B
                 \
feature:           C---D

After merge (fast-forward):
main:    A---B---C---D

```

### ✅ Pros:

- Clean history (no extra merge commits).
- Simpler for linear development.

### ❌ Cons:

- You lose the visibility of when branches were merged.

---

### 🔀 2. Three-Way Merge

### ✅ Definition:

A **three-way merge** occurs when the two branches have **diverged**, meaning both have unique commits. Git uses the **common ancestor** (merge base), the **source branch**, and the **target branch** to perform the merge.

### 📘 Example:

```bash
# You're on main
git merge feature

```

If `main` has commits not in `feature`, Git performs a three-way merge.

### 📈 Visual:

```
Common ancestor: A
main:            A---B---C
                         \
feature:                  D---E

After merge:
main: A---B---C---------M
                        / \
                      D---E (merge commit M)

```

### ✅ Pros:

- Retains the history of both branches.
- Useful in collaborative workflows (e.g., GitHub pull requests).

### ❌ Cons:

- Creates merge commits, which can clutter history.

---

### ⚖️ Summary Comparison Table:

| Feature | Fast-Forward Merge | Three-Way Merge |
| --- | --- | --- |
| **Divergence** | No (linear history) | Yes (branches diverged) |
| **Merge Commit** | No | Yes |
| **History** | Cleaner, linear | Preserves branching history |
| **Use Case** | Solo development, small changes | Collaboration, multiple contributors |
| **Command Example** | `git merge branch` | `git merge branch` (with divergence) |

---

### 💡 Tip:

To **force a three-way merge** (and preserve branch history) even when a fast-forward is possible, use:

```bash
git merge --no-ff branch_name

```

---