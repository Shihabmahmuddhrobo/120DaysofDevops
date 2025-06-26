# git switch, git branch, and git checkout

---

## 🔁 `git switch` (Introduced in Git 2.23+)

### Purpose:

- To **switch between branches** (and optionally create new ones with `b`).
- Designed to be **clearer and safer** than `git checkout`.

### Common Usage:

```bash
git switch <existing-branch>        # switch to an existing branch
git switch -b <new-branch>          # create and switch to a new branch

```

### Pros:

- Easier to understand for beginners.
- Less risky (e.g., won’t accidentally change files like `git checkout` might).

---

## 🌿 `git branch`

### Purpose:

- To **list**, **create**, **rename**, **copy**, or **delete** branches.
- **Does not switch** to another branch.

### Common Usage:

```bash
git branch                   # list branches
git branch <name>           # create a new branch
git branch -d <name>        # delete a branch
git branch -m old new       # rename a branch
git branch -c old new       # copy a branch (since Git 2.30)

```

### Example:

```bash
git branch feature/login     # creates a new branch
git switch feature/login     # switches to it

```

---

## 🧭 `git checkout`

### Purpose:

- **Multifunctional**, but often used to switch branches or restore files.
- Considered a bit **overloaded/confusing**, which is why `git switch` and `git restore` were introduced.

### Common Usage:

```bash
git checkout <branch>            # switch to a branch
git checkout -b <new-branch>     # create and switch to new branch
git checkout -- <file>           # discard local changes to a file

```

### Legacy:

- Still works and is widely used, but for clarity:
    - Use `git switch` for branches.
    - Use `git restore` for files.

---

## 🔍 Summary Table

| Command | Action | Notes |
| --- | --- | --- |
| `git switch <b>` | Switch branches | Modern and safe |
| `git switch -b <b>` | Create + switch branch | Preferred way to create branches now |
| `git branch <b>` | Create branch only | Doesn’t switch to it |
| `git checkout <b>` | Switch branches | Older style, still valid |
| `git checkout -b <b>` | Create + switch branch | Legacy equivalent of `git switch -b` |
| `git branch -d <b>` | Delete branch | Doesn’t switch |
| `git branch -m a b` | Rename branch | Modern method |
| `git branch -c a b` | Copy branch (2.30+) | Copies without switching |

---