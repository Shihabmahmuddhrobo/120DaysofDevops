# What is the Staging Area in Git?

## What is the Staging Area in Git?

The **staging area** (also called the **index**) is like a **waiting room** where you **prepare your files** before saving them permanently in a **commit**.

### 🔁 Git has 3 main parts:

1. **Working directory**: The files you are currently editing.
2. **Staging area (index)**: Files you choose to **include** in your next commit.
3. **Repository**: The permanent place where your **committed** changes are stored.

---

## 🧴 Real-Life Example:

Imagine you’re writing a **report** with 3 files:

- `report.txt`
- `data.csv`
- `summary.md`

Now let’s say:

- You changed **all 3 files**, but you only want to **commit** the change in `report.txt` first.
- You run:

```bash
bash
CopyEdit
git add report.txt

```

Now:

- `report.txt` is in the **staging area** ✅
- `data.csv` and `summary.md` are still in the **working directory** ❌

Then you run:

```bash
bash
CopyEdit
git commit -m "Update report content"

```

Only `report.txt` gets saved into the repository.

The other files are untouched (not committed yet).

---

## 🔧 Basic Commands

| Action | Command |
| --- | --- |
| Check what’s staged | `git status` |
| Add file to staging | `git add filename` |
| Add all changed files | `git add .` |
| Remove a file from staging | `git restore --staged filename` |
| Commit staged files | `git commit -m "message"` |

---

## 🎯 Why is the Staging Area Useful?

- You control **what exactly goes into each commit**
- You can **split up your changes** into smaller, meaningful commits
- It helps keep your Git history **clean and readable**

---

### 🧪 Example Workflow:

```bash
bash
CopyEdit
# You edit three files
nano file1.txt
nano file2.txt
nano file3.txt

# You check status
git status

# You stage only one
git add file1.txt

# You check status again
git status

# You commit
git commit -m "Updated file1 only"

# file2 and file3 still uncommitted

```