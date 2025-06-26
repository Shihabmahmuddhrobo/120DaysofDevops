# Git Checkout vs Restore

## ✅ `git restore filename.txt` (✅ Recommended in Git 2.23+)

- **Introduced in Git 2.23** to make Git commands easier to understand.
- Specifically meant for restoring file contents.

### 🔹 Behavior:

- Discards changes in the **working directory**.
- Restores the file to its last committed state (HEAD).

### 🔹 Example:

```bash
git restore index.html

```

> Discards local changes to index.html and resets it to the version in the last commit.
> 

---

## ⚠️ `git checkout filename.txt` (⚠️ Legacy use)

- Before Git 2.23, this was used for multiple things: switching branches **and** restoring files.
- Still works, but **less clear**, especially for beginners.

### 🔹 Behavior:

- Same effect: resets the file to the version in HEAD.

### 🔹 Example:

```bash
git checkout index.html

```

> Also discards changes in index.html and restores it from the last commit.
> 

---

## 🧠 Key Differences

| Feature | `git restore` | `git checkout` |
| --- | --- | --- |
| Purpose-built for file restoration | ✅ Yes | ❌ No (used for branch switching too) |
| Clearer syntax | ✅ Yes | ❌ No (can be confusing) |
| Introduced in | Git 2.23+ | Always available |
| Also used for switching branches | ❌ No | ✅ Yes |

---

## 🔧 Best Practice

- ✅ Use `git restore` for **restoring files**
- ✅ Use `git switch` for **changing branches**
- ❌ Avoid `git checkout` for both unless you're using older Git

---