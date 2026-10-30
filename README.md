# GitHub Actions JAR Runner

This repository is configured to automatically run `demo-0.0.1-SNAPSHOT.jar` using **GitHub Actions**.

---

## 📁 Repository Structure

```text
├── .github/
│   └── workflows/
│       └── run-jar.yml          # GitHub Actions workflow definition
├── demo-0.0.1-SNAPSHOT.jar      # Spring Boot application JAR file
├── .gitignore                   # Git ignore file (preserves the JAR)
└── README.md                    # Instructions & Documentation
```

---

## 🚀 How to Push to GitHub

If you haven't pushed this folder to GitHub yet, run these commands in your terminal or PowerShell inside this folder:

```bash
# 1. Initialize Git repository
git init

# 2. Add all files (including the JAR and workflow)
git add .

# 3. Commit the files
git commit -m "Add JAR file and GitHub Actions workflow"

# 4. Set main branch
git branch -M main

# 5. Link to your GitHub repository (replace with your repository URL)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git

# 6. Push to GitHub
git push -u origin main
```

---

## ⚙️ How the GitHub Action Works

Once pushed to GitHub:

1. **Automatic Execution**: The workflow runs automatically whenever you push to `main` or `master`.
2. **Manual Execution**: You can also trigger it manually:
   - Go to your repository on GitHub.
   - Click on the **Actions** tab.
   - Select **Run JAR Application** on the left.
   - Click **Run workflow**, choose how many seconds to keep it running, and click the green button.
3. **Execution Steps**:
   - Clones your repository with JDK 21 setup.
   - Boots `demo-0.0.1-SNAPSHOT.jar`.
   - Waits for the Spring Boot application to start (`Started DemoApplication`).
   - Displays all server startup logs and banners in the GitHub Actions console.
   - Pings `http://localhost:8080`.
   - Shuts down the application gracefully and archives `app.log` as a workflow artifact.
