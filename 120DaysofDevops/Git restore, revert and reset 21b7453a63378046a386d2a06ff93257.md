# Git restore, revert and reset

---

## 🔧 1. `git restore`

**Use it to undo changes in your working directory or staging area (index).**

Introduced in Git 2.23+ to replace some confusing uses of `checkout`.

### 🔹 Use Cases:

- Discard local changes in a file.
- Unstage a file from the index.

### 🔹 Examples:

**Discard changes in a file (go back to last commit):**

```bash
git restore filename.txt

```

**Unstage a file (but keep changes):**

```bash
git restore --staged filename.txt

```

---

## ♻️ 2. `git revert`

**Use it to undo a commit by creating a new "undo" commit.**

✅ Safe for shared/public branches like `main`.

### 🔹 Use Case:

- Revert a commit without altering Git history.

### 🔹 Example:

```bash
git revert abc1234

```

- This will **create a new commit** that undoes the changes made by commit `abc1234`.

![image.png](Git%20restore,%20revert%20and%20reset%2021b7453a63378046a386d2a06ff93257/image.png)

---

## 🔁 3. `git reset`

**Use it to move `HEAD` and optionally modify the index and working directory.**

Can **rewrite history** (⚠️ be careful on shared branches).

### 🔹 3 Modes:

| Mode | Affects Staging? | Affects Files? | Description |
| --- | --- | --- | --- |
| `--soft` | ✅ Yes | ❌ No | Keep file changes, reset only the commit history |
| `--mixed` (default) | ✅ Yes | ✅ No | Reset commit history and staging area |
| `--hard` | ✅ Yes | ✅ Yes | Discard everything — commits, staged changes, and files |

### 🔹 Examples:

**Undo last commit but keep changes staged:**

```bash
git reset --soft HEAD~1

```

**Undo last commit and unstage the changes:**

```bash
git reset --mixed HEAD~1

```

**Dangerous: erase commit and file changes:**

```bash
git reset --hard HEAD~1

```

---

## 🧠 Summary Table

| Command | Affects Commits? | Affects Index (Staging)? | Affects Working Dir? | Safe for Public Branches? |
| --- | --- | --- | --- | --- |
| `git restore` | ❌ No | ✅/❌ (optional) | ✅/❌ (optional) | ✅ Yes |
| `git revert` | ✅ Yes (adds new) | ❌ No | ❌ No | ✅ Yes |
| `git reset` | ✅ Yes | ✅ Yes | ✅ Yes (`--hard`) | ❌ No (except in local) |

---