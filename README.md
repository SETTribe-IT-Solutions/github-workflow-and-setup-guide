# GitHub Workflow & Setup Guide

This document outlines the standard operating procedures for setting up your development environment, managing repositories, and contributing code using Git and GitHub.

## 1. Requirements
Before starting, ensure the following software is installed and accounts are set up:
- **XAMPP** – Local server environment (Apache/MySQL)
- **Git** – Version control system
- **GitHub Account**
- **VS Code** – Preferred IDE

## 2. Installation
Ensure you install the software in the default recommended directories unless you have a specific custom setup.
- Install Git (default settings)
- Install XAMPP (select Apache & MySQL)
- Install VS Code  

## 3. Configuration (First Time Only)
Open your terminal (Git Bash or Command Prompt) and configure your global identity. This ensures your commits are attributed to you.
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

## 4. Workspace Setup
We organize all projects within the XAMPP `htdocs` directory.
1. Navigate to your XAMPP installation folder (usually C:\xampp\htdocs).
2. Create a new folder named `repos`.
- Path: `C:\xampp\htdocs\repos\`

## 5. Repository Access
Ensure your GitHub username has been added as a collaborator to the organization or specific repository. You should receive an email invitation; accept it to gain access.

## 6. Clone Repository
Cloning downloads the project from GitHub to your local machine.
1. Open your terminal/command prompt.
2. Navigate to your repos folder:
```bash
cd C:/xampp/htdocs/repos
```
3. Run the clone command:
```bash
git clone <repo_url>
```

## 7. Open in VS Code
1. Open VS Code.
2. Go to File > Open Folder.
3. Select the project folder you just cloned (e.g., C:\xampp\htdocs\repos\<project_name>)

## 8. Create New Branch
Never work directly on the `main` or `master` branch. Always create a new branch for your specific task.
**Naming Convention:** `<dev_name>_<task_name>`
1. Open the terminal in VS Code (Ctrl + ~).
2. Create and switch to a new branch:
```bash
git checkout -b "Mayuresh_Create_Dummy_Page"
```
- `checkout`: Switches branches.
- `-b`: Creates a new branch if it doesn't exist.

## 9. Development
Perform your coding tasks, bug fixes, or feature additions in VS Code. Ensure your XAMPP Apache servers are running if you need to test locally.

## 10. Add to Staging
Once your work is done, you must stage the files you want to save.
To add a specific file:
```bash
git add filename.php
```
To add ALL changed files (Recommended):
```bash
git add .
```

## 11. Commit Changes
Committing saves the staged changes to your local history.
```bash
git commit -m "Commit message"
```
  **Note**: Keep your commit messages clear and descriptive.

## 12. Push to GitHub
Pushing uploads your local commits to the remote GitHub server.
**Option A:** If the branch already exists remotely
```bash
git push
```
**Option B:** First time pushing this new branch (Recommended)You will likely see an error asking to set upstream. Run this:
```bash
git push --set-upstream origin <branch_name>
```

## 13. Pull Request (PR)
Once your code is pushed, you need to merge it into the main codebase
1. Open your repository on GitHub.
2. Navigate to the Pull Requests tab.
3. Click the green New Pull Request button.
4. Select Branches:
  - **Base**: main (Where the code is going)
  - **Compare**: <Your_Branch_Name> (Where your code is coming from)
  - **Example**: Compare: Mayuresh_Create_Dummy_Page
5. Add a title and description for your PR.
6. Click Create Pull Request.
7. Wait for any code reviews (if applicable).
8. Once approved, click Merge Pull Request.

## 14. Update Local Repository
After your Pull Request has been merged, your local main branch will be behind the remote version. Before starting a new task, you must update your local repository.
1. Switch back to the main branch:
```bash
git checkout main
```
3. Pull the latest changes from GitHub:
```bash
git pull
```
5. Create a new branch for your next task:
```bash
git checkout -b "<new_branch>"
```
