# Git switch -b vs Git branch -c

---

### ✅ `git switch -b <branch-name>`

- **Creates** a new branch and **switches** to it.
- Equivalent to `git checkout -b <branch-name>`.
- The `b` flag stands for **branch**.

```bash
git switch -b new-feature

```

---

### 🧐 `c` is used with a **different command**: `git branch`

When you use `-c`, it's in the context of the `git branch` command:

```bash
git branch -c <old-branch> <new-branch>

```

This **copies** (i.e., **renames**) an existing branch.

So:

```bash
git branch -c dev backup-dev

```

creates `backup-dev` as a **copy of `dev`**, then keeps both branches.

---

### TL;DR

| Command | Purpose |
| --- | --- |
| `git switch -b <name>` | Create and switch to a new branch |
| `git branch -c <old> <new>` | Copy an existing branch to a new one |