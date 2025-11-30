Day 11 – GitHub Actions CI Pipeline

This project demonstrates a simple CI/CD pipeline using GitHub Actions.
Whenever new code is pushed to the repository, an automated workflow runs to:

Check out the code

Set up Python

Install dependencies (if any)

Run the Python script (app.py)

Show the output in GitHub Actions logs

✅ CI Status Badge

(This will automatically turn green ✔ after a successful pipeline run)

![CI Status](https://github.com/SONU8294/day11_github_actions/actions/workflows/python-ci.yml/badge.svg)

📁 Project Structure
day11_github_actions/
│
├── app.py
└── .github/
    └── workflows/
        └── python-ci.yml

🧪 What This Pipeline Does

The GitHub Actions workflow:

✔ Triggers on every push
✔ Uses Python 3.x
✔ Checks the script by running:

python app.py


This ensures your code works before merging or deploying.

🐍 Python Script (app.py)
print("Hello CI/CD")

🔁 GitHub Actions Workflow (python-ci.yml)
name: Python CI

on:
  push:
    branches: [ "main" ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - name: Checkout Repository
      uses: actions/checkout@v3

    - name: Setup Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.x'

    - name: Run Python Script
      run: python app.py

🚀 How to Use

Clone the repository

Update app.py

Push your changes

GitHub Actions will run automatically
