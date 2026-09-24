# 🚀 TelekomSNTest – ServiceNow Git Source Control Integration

This repository serves as a testing and demonstration environment for integrating ServiceNow with Git-based **Source Control**.

> 🎯 **Goal:** Replace traditional Update Set-based development and deployment processes with a modern, CI/CD-ready, fully traceable version control workflow.

---

## 🎯 What is this and why are we using it?

We utilize the native Git integration within ServiceNow **Studio / App Engine Studio (AES)** for Scoped Application development.

### Key Benefits over Update Sets:
- **Version Control:** Line-by-line code tracking (`Git commit history`).
- **Clear Code Reviews:** Before merging changes into the main branch (`main`), code can be reviewed via Pull Requests (PRs).
- **Parallel Development:** Developers can work on their own feature branches without overwriting each other's work or causing collisions.
- **CI/CD Enablement:** Lays the foundation for future automated testing (ATF) and deployment pipelines.

---

## 🛠️ Developer Guide (Step-by-Step Workflow)

### 1. Prerequisites & Setup
You will need a **Personal Access Token (PAT)** from your GitHub account:
1. Go to GitHub Profile ➔ **Settings** ➔ **Developer Settings** ➔ **Personal Access Tokens (Tokens classic)**.
2. Generate a new token with `repo` scope permissions and save the generated key securely.

---

### 2. Linking the Repository to the ServiceNow Instance
1. Open ServiceNow **Studio** (`System Applications > Studio`).
2. Open the Scoped App.
3. Navigate to **Source Control > Link to Source Control**.
4. Enter the required details:
   - **URL:** `https://github.com/GergoSzecsei/TelekomSNTest.git`
   - **Credential:** Create a new record (GitHub username + PAT Token).
   - **Branch:** `main`

---

### 3. Daily Development Workflow

> ⚠️ **DO NOT develop directly on the `main` branch!**

#### A) Starting a New Feature
1. In Studio: **Source Control > Create Branch**
2. Naming convention: `feature/STORY-XXXX-description` (e.g., `feature/STORY-1234-approval-flow`)

#### B) Development & Commit
1. Complete your development in Studio (Business Rules, Script Includes, Flows, etc.).
2. Once a logical unit of work is ready: **Source Control > Commit Changes**
3. Select the modified files and write a clear commit message:
   ```text
   STORY-1234: Added approval script for catalog item

# TelekomSNTest
