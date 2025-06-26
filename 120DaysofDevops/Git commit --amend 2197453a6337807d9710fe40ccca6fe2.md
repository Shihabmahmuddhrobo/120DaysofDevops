# Git commit --amend

---

## 🧠 What is `git commit --amend`?

It **modifies your last commit**.

You can use it to:

- Fix a typo in the last commit message
- Add new files you forgot to include
- Change the content of the last commit (without creating a new one)

> 🧾 Think of it like saying:
> 
> 
> “Oops! I forgot something in my last commit. Let me fix that.”
> 

---

## ✅ Example 1: Fix Last Commit Message

Let's say you ran:

```bash
git commit -m "Finshed login page"

```

Oops! Typo: *Finshed* should be *Finished*

Run:

```bash
git commit --amend -m "Finished login page"

```

✅ Now the message is corrected.

⚠️ This **replaces** the previous commit with a new one.

---

## ✅ Example 2: Add File You Forgot

You committed this:

```bash
git commit -m "Added login.html"

```

But you forgot to include `style.css`!

### Step-by-step fix:

```bash
git add style.css
git commit --amend

```

Now:

- Git opens your editor (e.g. Vim or VS Code)
- You can **keep or change** the commit message
- Both `login.html` and `style.css` will now be in that one commit

---

## ⚠️ Warning: Use with Care!

Only use `--amend` when your last commit **has NOT been pushed to a shared repo**.

Because:

- `-amend` **replaces the commit** (changes its ID)
- If others already pulled it, it can **cause conflicts**

> ✅ Safe when working alone or before git push
> 
> 
> ❌ Risky after pushing to GitHub or team repo
> 

---

## 🧪 Summary Table

| Task | Command |
| --- | --- |
| Fix last commit message | `git commit --amend -m "New msg"` |
| Add missing files to last commit | `git add file && git commit --amend` |
| Open editor to edit commit | `git commit --amend` |

---