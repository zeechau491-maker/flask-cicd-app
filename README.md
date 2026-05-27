# ⚙️ CI/CD Pipeline with GitHub Actions

A fully automated CI/CD pipeline built with GitHub Actions. Every time code is pushed to the main branch, the pipeline automatically runs tests, builds a Docker image, and pushes it to Docker Hub — zero manual steps required.



-----

## 📋 What It Does

- ✅ Triggers automatically on every push to main branch
- ✅ Runs automated tests using pytest
- ✅ Stops the pipeline if any test fails — nothing broken reaches Docker Hub
- ✅ Builds a Docker image on every successful test run
- ✅ Pushes the image to Docker Hub automatically
- ✅ Uses GitHub Secrets for secure credential management

-----

## 🗃️ Project Structure

```
cicd-pipeline/
├── .github/
│   └── workflows/
│       └── ci.yml          # Pipeline definition — the heart of this project
├── tests/
│   └── test_app.py         # Automated tests that run on every push
├── app.py                  # Flask web application
├── Dockerfile              # Builds the Docker image
├── requirements.txt        # Python dependencies
├── .gitignore              # Excludes sensitive files from Git
└── README.md               # You are here
```

-----

## ⚙️ How The Pipeline Works

```
Developer pushes code to GitHub (main branch)
           │
           ▼
    GitHub Actions triggers
           │
           ▼
      ┌────────────┐
      │  TEST JOB  │  ← Installs dependencies, runs pytest
      └────────────┘
           │
     Tests pass? ──── NO ──→ Pipeline stops. Nothing gets built.
           │
          YES
           ▼
   ┌────────────────────┐
   │  BUILD & PUSH JOB  │  ← Builds Docker image, pushes to Docker Hub
   └────────────────────┘
           │
           ▼
    Docker Hub updated ✅
-

## 👤 Author

**Zee** — Transitioning into DevOps | AWS Cloud Practitioner
Building a DevOps portfolio from the ground up.
