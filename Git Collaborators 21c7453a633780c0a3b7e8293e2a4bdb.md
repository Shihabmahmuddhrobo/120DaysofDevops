# Git Collaborators

A **collaborator** is someone you **invite to directly contribute** to your **private GitHub repository**.
They get **write access** by default — which allows them to:
• Clone the repo
• Push commits
• Create branches
• Create/push to pull requests
• Review or merge PRs (if allowed by settings)
For public repos, anyone can fork, but **collaborators are trusted users** who work directly on the same repo.
**🧭 How to Add a Collaborator**
1. Go to your repository on GitHub.
2. Click the **Settings** tab (⚙️).
3. In the left sidebar, click **Collaborators & teams** (or **Manage access**).
4. Click **Invite a collaborator**.
5. Enter the **GitHub username** or email of the person.
6. Click **Add [username] to this repository**.⚠️ You must be the **owner** of the repo or have **admin access** to do this.
**🛂 Collaborator Permissions**
By default:
• **Write** access: Can push branches and create pull requests.
• You can also give:
    ◦ **Read**: View and clone only
    ◦ **Admin**: Manage settings, collaborators, and branches
    ◦ **Maintain / Triage**: (Advanced roles — useful in orgs)
👉 You can configure these in **Settings > Manage Access**.
**🔐 For Organizations**
If the repo is under a **GitHub organization**, you manage access via:
• **Teams** and their permission levels
• **Fine-grained access** per team or member
**🚫 Removing a Collaborator**
1. Go to **Settings > Collaborators & teams**.
2. Click the **trash icon 🗑️** next to their name.
**✅ After You Invite Them**
• They'll get an **email invite**.
• Once accepted, they can **clone the repo**:

`git clone https://github.com/yourusername/your-repo.git`

**💡 Bonus Tip: Private Repo Limits**
• Free GitHub accounts can add **collaborators** to **private repos**.
• For **more control** (e.g., roles, teams), use **GitHub Organizations**.