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

## 🌐 10. Official Project Links

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


