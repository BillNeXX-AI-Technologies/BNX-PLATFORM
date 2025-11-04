# BNX PLATFORM


Intern → feature/frontend-ui → Pull Request → dev → main → Deployment
Perfect ✅
Below is the **complete 7-step Git branching workflow** — from the main site (production) to feature development — written clearly so you can **directly paste it in your `README.md`** for your intern or team to understand 👇

---

# 🧠 BillNeXX Git Branching Workflow

This document explains how to work with Git branches in **BillNeXX** project — from local setup to production merge.
It helps developers collaborate without breaking the live (main) version.

---

## 🪜 Step 1: Clone the Repository

First, every developer must clone the latest version of the BillNeXX repository:

```bash
git clone https://github.com/ravivit/BillNexx.git
cd BillNexx
```

👉 This downloads the project code and moves you into the project folder.

---

## 🪜 Step 2: Checkout the Main Branch

The **main** branch is the stable, production-ready version of the site (the live website).

```bash
git checkout main
git pull origin main
```

👉 This ensures you’re working on the latest, clean version before creating or merging anything.

---

## 🪜 Step 3: Create and Switch to the Dev Branch

The **dev** branch is used for **testing, staging, and development** before pushing to main.

```bash
git checkout -b dev
```

If dev already exists, simply switch to it:

```bash
git checkout dev
git pull origin dev
```

👉 All new features and bug fixes should be tested here before merging into main.

---

## 🪜 Step 4: Create a New Feature Branch

When working on a specific feature, always create a **feature branch** from the dev branch.
Use the naming format: `feature/<feature-name>`

Example:

```bash
git checkout dev
git pull origin dev
git checkout -b feature/frontend-ui
```

👉 This isolates your work so you don’t break other code.

---

## 🪜 Step 5: Make Changes & Commit

Edit your files locally. Once done, **commit your changes** clearly:

```bash
git add .
git commit -m "Added new responsive frontend UI components"
```

👉 Always write meaningful commit messages (describe what was changed or added).

---

## 🪜 Step 6: Push the Feature Branch to GitHub

After committing, push your feature branch to GitHub:

```bash
git push origin feature/frontend-ui
```

👉 Now your branch appears on GitHub under **Branches → feature/frontend-ui**.

---

## 🪜 Step 7: Merge Workflow

Follow this 3-step merge path:

### 🔹 Step 7.1 → Merge Feature → Dev

When the feature is tested and approved, merge it into the `dev` branch:

```bash
git checkout dev
git pull origin dev
git merge feature/frontend-ui
git push origin dev
```

👉 The dev branch now has the latest tested feature.

---

### 🔹 Step 7.2 → Merge Dev → Main (for Production)

After full testing on dev, push the final code to **main** for deployment:

```bash
git checkout main
git pull origin main
git merge dev
git push origin main
```

👉 This updates the live production site with the tested code.

---

### 🔹 Step 7.3 → Delete Old Feature Branch (Optional)

To keep the repo clean:

```bash
git branch -d feature/frontend-ui
git push origin --delete feature/frontend-ui
```

---

## 🧩 Branch Structure Summary

```
main  →  Live Production (Stable)
│
└── dev  →  Development & Testing
     │
     └── feature/frontend-ui  →  Individual Feature Work
```

---

## 🚀 Example Real Workflow

**Example: You’re building a new dashboard page**

1. `git checkout main` → Start from latest main
2. `git checkout dev` → Switch to dev
3. `git checkout -b feature/dashboard-ui` → Create new feature
4. Make code changes → Save and test
5. `git add . && git commit -m "Added new dashboard page"`
6. `git push origin feature/dashboard-ui`
7. Create Pull Request → Merge to dev
8. After testing → Merge dev → main → deploy live 🚀

---

## ✅ Golden Rules

* Never commit directly to `main`
* Always branch from `dev`
* Always write clear commit messages
* Merge feature → dev → main
* Test everything before pushing to main

---

Would you like me to make this **README.md** file (ready for upload with emojis, code formatting, and section headers)?
I can export it as `.md` or `.pdf` for you.

