# Aceest Fitness App
________________________________________
## Project Overview
Aceest Fitness is a Flask-based web application designed for managing gym operations efficiently.
It tracks members, workouts, and general gym management tasks.
The application is Dockerized for consistent deployment and integrates a CI/CD pipeline using GitHub Actions for automated testing and Docker image building.
________________________________________
## Objective
The main objective is to provide a lightweight, maintainable, and testable web application for gym management.

Key Goals:
* Simplify gym operations and member tracking
* Implement a containerized setup for consistent environments
* Automate testing and deployment using CI/CD
________________________________________
## Tech Stack
* Backend: Python 3.11, Flask
* Testing: Pytest
* Containerization: Docker
* CI/CD: GitHub Actions
* Version Control: Git & GitHub
* Optional Libraries: matplotlib
________________________________________
## Features
* User-friendly web interface for gym management
* Flask route testing using Pytest
* Dockerized environment for consistent deployment
* CI/CD pipeline to automate tests and Docker builds
* Easily extendable for additional gym management features
________________________________________
## Project Structure
```
Aceest-Fitness/
├─ app.py                  # Main Flask app
├─ Dockerfile              # Docker setup
├─ requirements.txt        # Python dependencies
├─ test_app.py             # Pytest test file
├─ .github/
│   └─ workflows/
│       └─ main.yml        # GitHub Actions workflow
```
________________________________________
## Setup Instructions
Prerequisites
```
•	Python 3.11+
•	Docker Desktop
•	Git
•	GitHub account (for CI/CD)
```
________________________________________
Local Setup

Clone the repository:
```
git clone <repository-url>
cd Aceest-Fitness
```
________________________________________
Create Virtual Environment (Optional)
```
python -m venv venv
Activate:
•	Windows:
venv\Scripts\activate
•	Linux/macOS:
source venv/bin/activate
```
________________________________________
Install Dependencies
```
pip install --upgrade pip
pip install -r requirements.txt
```
________________________________________
## Running Locally
```
python app.py
Open your browser at:
http://127.0.0.1:5000
```
________________________________________
## Running Tests
```
pytest -v test_app.py
Ensure required modules (like matplotlib) are installed.
```
________________________________________
## Docker Setup
Build Docker Image
```
docker build -t aceest-app .
```
Run Docker Container
```
docker run -p 5000:5000 aceest-app
Access the application at:
http://localhost:5000
```
________________________________________
## CI/CD with GitHub Actions
The pipeline is triggered on every:
* push
* pull request

Workflow File
```
.github/workflows/main.yml
```
Steps in Workflow

1.	Checkout code
2.	Set up Python 3.11
3.	Install dependencies
4.	Run tests (pytest -v test_app.py)
5.	Build Docker image
________________________________________
## Key Learning Outcomes
* Built a Flask web application and structured routes effectively
* Used Pytest for testing Flask routes
* Implemented Docker containerization for consistent environments
* Set up CI/CD pipelines in GitHub Actions

Resolved real-world issues:
* ModuleNotFoundError
* Test discovery problems
* Docker host binding issues
________________________________________
## Conclusion
Aceest Fitness demonstrates a full-cycle application development process, including:
```
Development → Testing → Containerization → CI/CD Automation
```

This project provides a strong foundation for building scalable and maintainable web applications.
________________________________________

## Author
Muruganantham

Master’s in Software Engineering, BITS Pilani
