# Tracked vs untracked files in Git

## 🧠 What Are Tracked and Untracked Files in Git?

### 🔷 **Tracked Files**

These are the files Git **already knows about** — meaning:

- They were added using `git add`
- They are being monitored for changes
- They may be:
    - Unmodified (no change since last commit)
    - Modified (you changed them)
    - Staged (ready to commit)

> ✅ Think of tracked files like:
> 
> 
> *“I’ve told Git to keep an eye on these.”*
> 

---

### 🔶 **Untracked Files**

These are files that are **new** in your folder but **not yet added to Git**.

- Git doesn’t track changes in these files
- They won't be part of commits until you `git add` them

> ❌ Think of untracked files like:
> 
> 
> *“Git sees them, but is ignoring them for now.”*
> 

---

## 📂 Real-Life Example

Let’s say you have this folder:

```
pgsql
CopyEdit
my_project/
├── index.html       (tracked)
├── style.css        (tracked)
└── notes.txt        (new file = untracked)

```

Run:

```bash
bash
CopyEdit
git status

```

You will see something like:

```
yaml
CopyEdit
Changes not staged for commit:
  modified:   index.html
  modified:   style.css

Untracked files:
  notes.txt

```

- `index.html` and `style.css` = **tracked** (Git is watching them)
- `notes.txt` = **untracked** (Git doesn’t care yet)

Now you run:

```bash
bash
CopyEdit
git add notes.txt

```

Then `notes.txt` becomes **tracked**, and ready for commit.

---

## 🔧 Summary Table

| File Status | Tracked? | In Staging? | Committed? | Notes |
| --- | --- | --- | --- | --- |
| `file1.txt` | ❌ No | ❌ No | ❌ No | Newly created, untracked |
| `file2.txt` | ✅ Yes | ❌ No | ✅ Yes | Tracked but changed |
| `file3.txt` | ✅ Yes | ✅ Yes | ❌ No | Tracked and staged for commit |
| `file4.txt` | ✅ Yes | ❌ No | ✅ Yes | Tracked and unchanged |

---

## 🛠 Commands You’ll Use

| Task | Git Command |
| --- | --- |
| See what’s tracked/untracked | `git status` |
| Add untracked file to staging | `git add <filename>` |
| Add all untracked files | `git add .` |
| Stop tracking a file (keep it) | `git rm --cached <filename>` |
| Ignore untracked files permanently | Add to `.gitignore` file |