# Git configuration levels

---

### 🧠 What is Git configuration?

Git needs to know some information to work properly — like your name, email, how to handle line endings, which editor to use, etc. This information is stored in **Git configuration** files.

Git has **three levels** of configuration:

---

### 1. **System Level**

- Applies to **everyone on the computer**.
- Stored in a file like:
    - Linux/Mac: `/etc/gitconfig`
    - Windows: `C:\ProgramData\Git\config`
- Used by **all users and all repositories** on the system.
- Needs **admin/root** access to change.

🛠️ Example:

```bash
git config --system user.name "System User"

```

---

### 2. **Global Level**

- Applies to **just you** (your user account).
- Stored in:
    - `~/.gitconfig` or `~/.config/git/config`
- Used for **all repositories** you work on as your user.

🛠️ Example:

```bash
git config --global user.name "Your Name"

```

---

### 3. **Local Level**

- Applies to **one specific repository**.
- Stored inside the project folder:
    - `.git/config`
- This is the **most specific** setting and **overrides global and system** if there's a conflict.

🛠️ Example (run inside a Git project):

```bash
git config user.name "Project-Specific Name"

```

---

### 🎯 Priority Order (Highest wins):

1. **Local**
2. **Global**
3. **System**

That means Git checks local first, then global, then system.

---

### ✅ Quick Example:

Imagine your name is:

- System: "System User"
- Global: "Alice Smith"
- Local (in one repo): "Alice Dev"

Then inside that one repo, Git will use **"Alice Dev"** because local settings win.

---