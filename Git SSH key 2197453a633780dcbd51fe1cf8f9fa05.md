# Git SSH key

> You generate your own SSH key and share your public key with the company.
> 

### ✔️ Then the company does this:

- Adds your public SSH key to their GitHub organization or repo
- Gives you access (based on your role)
- Now you can `git clone`, `push`, `pull` via SSH

---

## 💡 Step-by-Step Example

### 👨‍💻 On your laptop:

1. **Generate SSH key** (if not already):

```bash
bash
CopyEdit
ssh-keygen -t ed25519 -C "your.email@company.com"

```

This creates:

- `~/.ssh/id_ed25519` (your **private key** — NEVER share)
- `~/.ssh/id_ed25519.pub` (your **public key** — share this)

---

### 📤 You send only this:

```bash
bash
CopyEdit
cat ~/.ssh/id_ed25519.pub

```

Send the output to your team lead or admin.

---

### 🏢 Company adds your public key to:

- GitHub → [Settings] → [SSH and GPG keys] (if personal access)
- GitHub → Organization/team → Developer access
- Git server (if internal repo)

---

### ✅ After setup:

You can use:

```bash
bash
CopyEdit
git clone git@github.com:company/repo.git

```

And Git won't ask for password anymore.

---

## 🚫 Important Notes

- You **never** receive the **company’s SSH key** — that would be a big security risk!
- You only give **your own public key**
- Multiple developers have different public keys, and GitHub supports managing them easily