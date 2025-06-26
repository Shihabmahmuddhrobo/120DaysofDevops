# Git Cherry-picking

### 🍒 What Is `git cherry-pick`?

`git cherry-pick` lets you **copy a specific commit** from one branch and **apply it to another branch** — like picking a single cherry from a tree 🍒.

---

### ✅ In Simple Words:

> "git cherry-pick takes one specific commit from somewhere (like main) and applies that exact change to your current branch."
> 

You’re not merging whole branches — just grabbing one commit.

---

### 🧪 Example Scenario

Let’s say your repo looks like this:

```
main:    A---B---C
                   \
feature:            D---E  (you're here)

```

Suppose commit `B` is a useful bug fix, and you want to apply just that to `feature`, without merging everything from `main`.

### 🧾 Command

```bash
git cherry-pick <commit-hash-of-B>

```

Now your `feature` branch becomes:

```
feature: D---E---B'

```

> ✅ B' is a copy of commit B, applied to feature. It has a new commit hash.
> 

---

### 📦 Common Use Cases

| Use Case | Why Use `cherry-pick`? |
| --- | --- |
| Bring a fix from `main` to a feature branch | Without merging all of `main` |
| Copy a commit between unrelated branches | Reuse code in different development tracks |
| Selectively apply commits after rebasing | Keep only what you need |

---

### ⚠️ Notes & Warnings

- Be careful with conflicts — `git cherry-pick` can result in merge conflicts if the context has changed.
- The cherry-picked commit **gets a new hash** (it’s not the same commit).

---

### 🛠️ Basic Command Usage

```bash
# Apply one commit
git cherry-pick <commit-hash>

# Apply a range of commits
git cherry-pick A^..C   # applies commits A, B, and C

# Continue after resolving conflicts
git cherry-pick --continue

# Abort cherry-pick if something goes wrong
git cherry-pick --abort

```

---

### 🧠 Summary

| Feature | `git cherry-pick` |
| --- | --- |
| What it does | Applies one or more specific commits |
| To which branch | Your **current branch** |
| Result | New commit(s) with same change, new hash |
| Use for | Selective commit transfer across branches |

---