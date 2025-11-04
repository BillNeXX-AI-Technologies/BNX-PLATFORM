# BNX PLATFORM
Intern → feature/frontend-ui → Pull Request → dev → main → Deploymen

# 🚀 BillNeXX-AI-Technologies – Complete Git Branching & Workflow Guide

Welcome to **BillNeXX-AI-Technologies** 🧠
This document explains how our team manages branches, pushes updates, and maintains stability in the **BNX-PLATFORM** project.

It is designed for **interns, developers, and contributors** to follow a **standard, safe, and scalable workflow** for version control.

---

## 🧭 1. Overview – Why We Use Git Branching

Git branching ensures:

* 🔹 **Code safety:** No one accidentally breaks the main (live) site.
* 🔹 **Team collaboration:** Each developer works independently on a separate branch.
* 🔹 **Proper testing:** All changes go through the `dev` branch before being released to production.
* 🔹 **Rollback ability:** If a bug appears, we can revert easily without data loss.

---

## 🧱 2. Branch Structure

Our branching model is **3-tiered**, simple yet powerful 👇

```
main  →  Live Production (Stable)
│
└── dev  →  Development / Testing
     │
     └── feature/<feature-name>  →  Individual Developer Work
```

### 🔹 Explanation:

* **main:**

  * This is the **production branch**.
  * Code here goes **live on the BillNeXX website**.
  * Only **approved, tested, and reviewed code** should be merged here.

* **dev:**

  * This is the **staging branch** where we test everything.
  * All developers merge their `feature` branches here first.
  * It acts as a “safe zone” for internal testing.

* **feature/***branch-name*:

  * Temporary working branches.
  * Each developer or intern creates their own branch for new features or bug fixes.
  * These branches are short-lived and deleted after merging into `dev`.

---

## 🪜 3. Step-by-Step Workflow

Follow these steps every time you work on a new task 👇

---

### 🪜 Step 1: Clone the Repository

Get the latest project files from GitHub.

```bash
git clone https://github.com/BillNeXX-AI-Technologies/BNX-PLATFORM.git
cd BNX-PLATFORM
```

💡 **Explanation:**
This downloads the complete project codebase from GitHub into your computer and navigates inside it.

---

### 🪜 Step 2: Checkout the Main Branch

Always start from the **main** branch and ensure it’s updated.

```bash
git checkout main
git pull origin main
```

💡 **Explanation:**
You’re now on the latest live version of BillNeXX’s platform. Never make changes here directly — use it only as a base for new branches.

---

### 🪜 Step 3: Switch or Create the Dev Branch

The `dev` branch is used for internal testing and integration.

If it already exists:

```bash
git checkout dev
git pull origin dev
```

If not:

```bash
git checkout -b dev
```

💡 **Explanation:**
All work before production should go through this branch. This ensures bugs are caught early.

---

### 🪜 Step 4: Create a New Feature Branch

Before working on any new feature, make your own branch:

```bash
git checkout dev
git pull origin dev
git checkout -b feature/<feature-name>
```

💡 **Example:**

```bash
git checkout -b feature/frontend-ui
```

💡 **Explanation:**
This isolates your code, so others can work freely. Once your feature is done, we’ll merge it safely into `dev`.

---

### 🪜 Step 5: Make Your Changes & Commit

Now edit your code and save your work using commits:

```bash
git add .
git commit -m "Added new frontend UI components for dashboard"
```

💡 **Explanation:**

* `git add .` adds all modified files.
* `git commit -m` saves a checkpoint with a message describing what changed.
  Always use **clear, meaningful messages** for better collaboration.

---

### 🪜 Step 6: Push Feature Branch to GitHub

Now upload your feature branch to GitHub so others can see it.

```bash
git push origin feature/frontend-ui
```

💡 **Explanation:**
This creates your branch remotely. The team lead or reviewer can now check your code.

---

## 🧩 4. Merging Process (With Full Explanation)

Merging is how we bring everyone’s work together. Follow this exact sequence 👇

---

### 🔹 Step 7.1: Merge Feature → Dev

Once your work is ready and tested locally:

```bash
git checkout dev
git pull origin dev
git merge feature/frontend-ui
git push origin dev
```

💡 **Explanation:**

* You switch to `dev`.
* Pull latest updates (so you don’t overwrite others’ work).
* Merge your feature branch.
* Push changes to the remote `dev` branch.

✅ Result:
Your feature is now part of the development build for testing.

---

### 🔹 Step 7.2: Merge Dev → Main (Production)

Once all features are tested and verified:

```bash
git checkout main
git pull origin main
git merge dev
git push origin main
```

💡 **Explanation:**
This is the **final stage** before deployment. The `main` branch now contains stable, production-ready code.
After this push, your **live site gets updated**.

---

### 🔹 Step 7.3: Clean Up (Optional)

After merging, remove old feature branches to keep your repo clean:

```bash
git branch -d feature/frontend-ui
git push origin --delete feature/frontend-ui
```

💡 **Explanation:**
Deletes local & remote copies of the branch — keeping the repository neat and lightweight.

---

## 💻 5. Real Example – Full Workflow in Action

Let’s assume you’re adding a **Billing Dashboard** feature 👇

```bash
# Step 1: Clone the repo
git clone https://github.com/BillNeXX-AI-Technologies/BNX-PLATFORM.git
cd BNX-PLATFORM

# Step 2: Start from main
git checkout main
git pull origin main

# Step 3: Switch to dev
git checkout dev
git pull origin dev

# Step 4: Create your feature branch
git checkout -b feature/billing-dashboard

# Step 5: Do your coding work
# (make UI, backend routes, etc.)

# Step 6: Commit changes
git add .
git commit -m "Added Billing Dashboard module with analytics"

# Step 7: Push to GitHub
git push origin feature/billing-dashboard

# Step 8: Open Pull Request → feature/billing-dashboard → dev
# Step 9: Test & approve → Merge dev → main (production)
```

---

## 🧩 6. Branch Naming Convention

| Branch Type     | Format           | Description                        |
| --------------- | ---------------- | ---------------------------------- |
| **Main**        | `main`           | Live production (stable)           |
| **Development** | `dev`            | Staging/testing branch             |
| **Feature**     | `feature/<name>` | New feature or module development  |
| **Hotfix**      | `hotfix/<name>`  | Urgent fixes for production issues |

💡 Example:

* `feature/payment-gateway`
* `feature/user-authentication`
* `hotfix/api-error-500`

---

## 🧭 7. Best Practices for Interns

✅ **Do this:**

* Always start from `dev`
* Push code to `feature/your-task`
* Keep commits small & meaningful
* Pull latest `dev` changes before merging
* Delete branches after merging

❌ **Never do this:**

* Don’t push directly to `main`
* Don’t merge without review
* Don’t overwrite others’ commits

---

## 📁 8. Folder Structure (BNX-PLATFORM)

```
BillNeXX-AI-Technologies/
│
├── BNX-PLATFORM/
│   ├── frontend/          # React + Tailwind UI Components
│   ├── backend/           # FastAPI backend APIs
│   ├── public/            # Static files, assets, logos
│   ├── .env.example       # Environment variables template
│   ├── README.md          # Project overview
│   └── package.json
│
└── docs/
    └── GIT_WORKFLOW.md    # This document
```

---

## ⚙️ 9. Golden Rules Summary

| ✅ Do                        | ❌ Don’t                 |
| --------------------------- | ----------------------- |
| Create branches from `dev`  | Work directly on `main` |
| Write clear commit messages | Use random messages     |
| Test before merging         | Merge untested code     |
| Pull before push            | Force push without pull |
| Delete old branches         | Leave unused branches   |

---

## 🌐 10. Social official Links

| Platform       | Link                                                              |
| -------------- | ----------------------------------------------------------------- |
| 🌍 Website     | [https://billnexx.com](https://billnexx.com)                      |
| 💼 LinkedIn    | [BillNeXX LinkedIn](https://www.linkedin.com/company/billnexx)    |
| 📸 Instagram   | [@billnexx_official](https://www.instagram.com/billnexx_official) |
| 🐦 X (Twitter) | [@BillNeXX](https://x.com/BillNeXX)                               |
| 💬 WhatsApp    | [Chat with Us](https://wa.me/message/BXJNEM56HOWSG1)              |

---

## 🧠 11. Developer Summary (In 5 Lines)

> 1️⃣ Code locally →
> 2️⃣ Commit →
> 3️⃣ Push to `feature/` branch →
> 4️⃣ Merge → `dev` →
> 5️⃣ Merge → `main` → 🚀 Live!

---

## 🏁 Final Note

Every developer at **BillNeXX-AI-Technologies** must follow this workflow to ensure:

* Code stability 🧩
* Smooth collaboration 🤝
* Safe deployment 🚀

> *“Move Fast — But Don’t Break Things.”* 💡

* 🧾 **Generate this as a `README.md` file (ready to upload to GitHub)**,
* or 🎨 **Convert it into a well-designed PDF with your logo and colors (for intern onboarding manual)**?















# 🚀 BillNeXX-AI-Technologies – Intern Git & Branching Guide (Ready-to-Upload)

Welcome to **BillNeXX-AI-Technologies** — BNX-PLATFORM 👋  
This guide is written for **interns and new contributors**. Paste this file as `README_FOR_INTERNS.md` or `README.md` inside `BNX-PLATFORM` on GitHub.

---

## 🧭 Branch Flow Overview
```
main  →  Live Production (Stable)
│
└── dev  →  Development & Testing
     │
     └── feature/<feature-name>  →  Individual Feature Work
```

---

## 1. Quick Summary (5 lines)
1. Clone the repo.  
2. Switch to `dev`.  
3. Create `feature/<task>` branch.  
4. Commit & Push.  
5. Open PR → Merge to `dev` → Test → Merge `dev` → `main`.

---

## 2. Full Step-by-Step (Beginner-friendly)

### Step 0 — One-time Git setup (on your laptop)
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```
This sets identity for your commits.

---

### Step 1 — Clone the repository
```bash
git clone https://github.com/BillNeXX-AI-Technologies/BNX-PLATFORM.git
cd BNX-PLATFORM
```

---

### Step 2 — Check current branch & update
```bash
git branch         # shows local branches, * means current branch
git checkout main
git pull origin main
```

---

### Step 3 — Switch to `dev` (create if not present)
```bash
git checkout dev
git pull origin dev
# OR if it doesn't exist locally:
git checkout -b dev
```

---

### Step 4 — Create your feature branch
Always create feature branches from `dev`:
```bash
git checkout dev
git pull origin dev
git checkout -b feature/<your-name>-<task>
# example:
git checkout -b feature/nikhil-homepage
```

---

### Step 5 — Work, commit, push
Edit files, test locally. Then:
```bash
git add .
git commit -m "feat(frontend): Add responsive homepage layout"
git push origin feature/nikhil-homepage
```

**Commit message tips:** short, start with type (feat/fix/docs/chore), then scope and short description.

---

### Step 6 — Create Pull Request (on GitHub)
1. Open repo → Click **Pull requests** → **New pull request**.  
2. Set **base** to `dev`, **compare** to your `feature/...` branch.  
3. Title: `feat(frontend): Add homepage`  
4. Description: What changed, how to test, screenshots (if UI).  
5. Assign reviewer (Ravi) and click **Create pull request**.

---

### Step 7 — Review → Merge → Test → Deploy
- Lead reviews PR, requests changes or approves.
- After merge to `dev`, QA and testing happen on `dev`.
- When `dev` is stable, lead merges `dev` → `main`.  
  ```bash
  git checkout main
  git pull origin main
  git merge dev
  git push origin main
  ```
- Production deployment is triggered from `main`.

---

### Step 8 — Clean up
After a branch is merged and no longer needed:
```bash
git branch -d feature/nikhil-homepage
git push origin --delete feature/nikhil-homepage
```

---

## 3. Naming conventions
- Feature: `feature/<feature-name>` (example: `feature/billing-dashboard`)  
- Fix: `fix/<issue>`  
- Hotfix: `hotfix/<issue>`  
- Docs/chore: `docs/<...>`, `chore/<...>`

---

## 4. Common mistakes & how to avoid them
- **Never commit directly to `main`.** Use feature branches.  
- **Always pull before pushing.** `git pull origin <branch>`  
- **Keep commits small and focused.** Easier to review.  
- **Don’t force-push (`--force`)** unless told and coordinated.

---

## 5. GitHub UI quick guide (for non-technical reviewers)
- **Code** tab → view files.  
- **Branches** → see all branches and statuses.  
- **Pull requests** → create & review PRs.  
- **Actions** → CI builds/tests (if configured).  
- **Projects / Issues** → task tracking (if used).

---

## 6. Example full workflow (billing dashboard)
```bash
git clone https://github.com/BillNeXX-AI-Technologies/BNX-PLATFORM.git
cd BNX-PLATFORM
git checkout main
git pull origin main
git checkout dev
git pull origin dev
git checkout -b feature/billing-dashboard
# code...
git add .
git commit -m "feat(billing): add dashboard with charts"
git push origin feature/billing-dashboard
# create PR (feature/billing-dashboard -> dev)
# after review, merge to dev, test, then merge dev -> main
```

---

## 7. Checklist before raising PR
- [ ] Branch created from latest `dev`  
- [ ] Code builds locally / UI tested on different screen sizes (if frontend)  
- [ ] No console errors / broken tests  
- [ ] Commit messages are clear  
- [ ] PR description contains testing steps and screenshots (UI)  

---

## 8. Contact & Support
If stuck, ping on:
- **Slack/WhatsApp**: BillNeXX group  
- **Repo PR**: add comments in PR and tag `@ravivit`  
- **Email**: contact@billnexx.com

---

## 9. Appendix (Helpful git commands)
```bash
# show current branch
git branch

# switch branch
git checkout dev

# create branch
git checkout -b feature/name

# push current branch
git push origin HEAD

# delete branch locally
git branch -d feature/name

# delete branch remotely
git push origin --delete feature/name
```

---

_End of guide — ready to be pasted as `README_FOR_INTERNS.md` or `README.md` in BNX-PLATFORM._


