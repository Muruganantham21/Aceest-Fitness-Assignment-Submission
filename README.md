Aceest Fitness App
Overview
Aceest Fitness is a Flask-based web application for gym management. This project includes a Dockerized setup and a CI/CD pipeline using GitHub Actions to automate testing and Docker image building.
Table of Contents
•	Prerequisites 
•	Project Structure 
•	Setup Instructions 
•	Running Locally 
•	Running Tests 
•	Docker Setup 
•	CI/CD with GitHub Actions 
•	Common Issues & Fixes 
Prerequisites
•	Python 3.11+ 
•	Docker Desktop 
•	Git 
•	GitHub account (for CI/CD) 
Project Structure
Aceest-Fitness/
├─ app.py                   # Main Flask app
├─ Dockerfile               # Docker setup
├─ requirements.txt         # Python dependencies
├─ test_app.py              # Pytest test file
├─ .github/
│   └─ workflows/
│       └─ main.yml         # GitHub Actions CI workflow
Setup Instructions
1.	Clone the repository: 
git clone <repository-url>
cd Aceest-Fitness
2.	Create virtual environment (optional but recommended): 
python -m venv venv
source venv/bin/activate   # Linux/macOS
venv\Scripts\activate      # Windows
3.	Install Python dependencies: 
pip install --upgrade pip
pip install -r requirements.txt
Running Locally
1.	Run the Flask app: 
python app.py
2.	Open your browser at http://127.0.0.1:5000 
Running Tests
Pytest is used for testing the Flask routes.
1.	Run tests locally: 
pytest -v test_app.py
Make sure all required modules (like matplotlib) are installed. Missing modules will cause ModuleNotFoundError.
Example test in test_app.py:
from app import app

def test_login_page():
    client = app.test_client()
    response = client.get("/")
    assert response.status_code == 200
Docker Setup
1.	Dockerfile: 
FROM python:3.11-slim

WORKDIR /app
COPY . .

RUN pip install -r requirements.txt

EXPOSE 5000

CMD ["python", "app.py"]
2.	Build Docker image: 
docker build -t aceest-app .
3.	Run Docker container: 
docker run -p 5000:5000 aceest-app
4.	Access the app at http://localhost:5000 
CI/CD with GitHub Actions
1.	Workflow YAML (.github/workflows/main.yml): 
name: CI Pipeline

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: 3.11

    - name: Install dependencies
      run: |
        pip install --upgrade pip
        pip install -r requirements.txt

    - name: Run tests
      run: |
        pytest -v test_app.py

    - name: Build Docker Image
      run: |
        docker build -t aceest-app .
2.	Notes: 
o	The workflow installs Python 3.11, installs dependencies, runs tests, and builds a Docker image. 
o	pytest -v test_app.py ensures tests run even if the file is in the project root. 
Common Issues & Fixes
Issue	Cause	Solution
ModuleNotFoundError: No module named 'matplotlib'	matplotlib not in requirements.txt	Add matplotlib to requirements.txt
collected 0 items or ImportError while importing test module	pytest can’t find test files	Ensure test files start with test_ and are in the right directory, or point pytest to the correct file/folder
Docker not accessible on host port	Flask app listening only on 127.0.0.1	In app.py, use app.run(host="0.0.0.0", port=5000)
GitHub Actions Node.js warning	Deprecated Node.js 20 actions	Optional: set FORCE_JAVASCRIPT_ACTIONS_TO_NODE24=true in workflow environment
Exit code 1 in CI	Tests failing or missing dependencies	Ensure requirements.txt is complete, tests pass locally
References
•	Flask Documentation 
•	Pytest Documentation 
•	Docker Documentation 
•	GitHub Actions 

