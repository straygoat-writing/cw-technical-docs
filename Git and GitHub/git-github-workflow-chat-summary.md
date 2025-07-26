# Git and GitHub for Technical Writers

## 🧠 Why Git and GitHub for Technical Writers?

### Main reasons:
- **Version control**: Track changes to files over time, revert to previous versions, and see who made what changes and when.
- **Collaboration**: Work easily with developers and other writers on shared documentation projects.
- **Integration**: Many developer-focused teams store docs alongside code and use automated systems (CI/CD) to publish content.

---

## 🛠️ Basic Setup Workflow

### Step 1: Install Git
Each writer installs [Git](https://git-scm.com/downloads) on their local machine.

Git is a **local** version control tool. It tracks changes in files and folders within a project (called a **repository**).

### Step 2: Create or Clone a GitHub Repository
GitHub is an **online hosting platform** for Git repositories.

You have two options:

#### Option A: Start on GitHub
1. Create a repository on GitHub.
2. Use the `git clone` command to copy the repo to your local machine. This creates a local Git-tracked folder connected to the GitHub repo.

```bash
git clone https://github.com/username/repo-name.git
```

#### Option B: Start Locally
1. Create a folder locally and initialize Git:

```bash
mkdir my-docs
cd my-docs
git init
```

2. Add a GitHub repo as the remote:

```bash
git remote add origin https://github.com/username/repo-name.git
```

---

## 📂 How Does Git Know Which Folders to Track?

Git doesn’t track folders by default. It tracks **files inside the folder** where you ran `git init` (or where you cloned the repo), and any subfolders inside that directory.

To track files:
1. Use `git add` to stage files.
2. Use `git commit` to save a snapshot.

```bash
git add myfile.md
git commit -m "Add first draft of user guide"
```

You don’t need to tell Git to track specific folders unless you want to exclude things. That’s what `.gitignore` is for (e.g., to ignore `.DS_Store` files or output folders).

---

## 🔄 Connecting Local and Remote (GitHub)

Once your local folder is cloned or initialized, and connected to GitHub with a remote, you can:

- **Pull** updates from GitHub:

```bash
git pull origin main
```

- **Push** your local changes to GitHub:

```bash
git push origin main
```

This syncs your local content with the GitHub repository.

---

## 🧪 Summary for Tech Writers

- Git = local version control.
- GitHub = cloud-based storage and collaboration platform for Git repositories.
- Workflow = clone → edit locally → commit → push.
- Great for collaborative documentation, version tracking, and working with developer teams.
- Many tools (like Markdown linters, static site generators) integrate smoothly with GitHub Actions or similar CI systems.

---

## ✅ Recommended Git Workflow for Technical Writers

### 🔁 clone → branch → edit locally → commit → push → pull request

This is a **branch-based workflow**, which is safer and better for collaboration.

---

### 🔹 1. Clone the Repository (first-time setup)

```bash
git clone https://github.com/org-name/repo-name.git
cd repo-name
```

---

### 🔹 2. Create a New Branch for Your Work

```bash
git checkout -b update-user-guide
```

---

### 🔹 3. Edit Locally

Make your changes in the Markdown or source files.

---

### 🔹 4. Stage and Commit Changes

```bash
git add .
git commit -m "Update user guide with new screenshots"
```

---

### 🔹 5. Push Your Branch to GitHub

```bash
git push origin update-user-guide
```

---

### 🔹 6. Create a Pull Request (PR)

On GitHub, click “Compare & pull request.” This allows others to review and merge your work into the main branch.

---

### 🔹 7. Update Your Branch if Needed

```bash
git checkout main
git pull origin main
git checkout update-user-guide
git merge main
```

---

## 🏁 Summary Table

| Step         | Command Example                              | Notes                              |
|--------------|-----------------------------------------------|-------------------------------------|
| Clone        | `git clone URL`                               | One-time setup                      |
| Branch       | `git checkout -b my-branch`                   | Safe editing                        |
| Edit         | *(local file edits)*                          | Use your preferred editor           |
| Commit       | `git add . && git commit -m "Message"`        | Save your work locally              |
| Push         | `git push origin my-branch`                   | Send to GitHub                      |
| Pull Request | *(via GitHub UI)*                             | Get feedback, merge changes         |

---

### 💡 Notes for Technical Writers

- Avoid working directly on `main`.
- Use descriptive branch names.
- Keep commits small and focused.
- Communicate clearly in pull request comments.
