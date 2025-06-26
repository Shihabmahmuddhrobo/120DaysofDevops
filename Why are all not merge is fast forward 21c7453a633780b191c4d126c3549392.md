# Why are all not merge is fast forward

---

### 🔁 What Is a Fast-Forward Merge?

A **fast-forward merge** happens when the branch you’re merging into is **directly behind** the branch you’re merging from, **with no divergent history**.

### ✅ Example of Fast-Forward:

```
main:   A---B
feature:     \
              C---D

```

If `main` hasn’t changed since the split, Git can just “move the pointer” forward:

```bash
git checkout main
git merge feature  # Fast-forward merge

```

Result:

```
main:   A---B---C---D

```

---

### 🔄 Why Some Merges Are *Not* Fast-Forward

A merge **can't be fast-forwarded** if the branches have **diverged**, i.e., both have new commits.

### ❌ Example of Non-Fast-Forward:

```
main:    A---B---C
feature:     \
              D---E

```

Now `main` and `feature` have both moved independently. A fast-forward is **not possible** here. Git needs to create a **merge commit** to reconcile the two:

```bash
git checkout main
git merge feature  # Creates a merge commit

```

Result:

```
        A---B---C
         \     \
          D-----E---M   (M = merge commit)

```

---

### 🧠 Reasons You Might Not Get a Fast-Forward:

1. **Both branches have new commits** (diverged).
2. **You explicitly disable fast-forward merges** with:
    
    ```bash
    git merge --no-ff
    
    ```
    
3. **Using pull with merge strategy**:
    
    ```bash
    git pull --no-ff
    
    ```
    
4. **The repository enforces merge commits** for tracking purposes (common in teams).

---

### 📌 TL;DR

| Situation | Fast-Forward Possible? |
| --- | --- |
| No commits on base branch | ✅ Yes |
| Both branches have commits | ❌ No (merge commit needed) |
| Forced `--no-ff` option used | ❌ No |