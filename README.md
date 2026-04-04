## Aceest Fitness App
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
*	User Login System (Admin)
*	Client Management
*	AI-based Program Generation
*	Workout Tracking
*	Membership Tracking
*	PDF Report Generation
*	Progress Chart Visualization
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
## GitHub Repository
https://github.com/Muruganantham21/Aceest-Fitness-Assignment-Submission
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
Local Setup Instructions

Clone the repository:
```
git clone https://github.com/Muruganantham21/Aceest-Fitness-Assignment-Submission
cd Aceest-Fitness-Assignment-Submission
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
```
## Access Application
```
Open your browser at:
http://127.0.0.1:5000
```
## Default Login
```
Username: admin
Password: admin
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
## Jenkins Integration
Jenkins is used as a build automation tool.
Functionality:
* Executes build pipeline
* Runs tests
* Validates application
Note:
Due to plugin/network constraints, Jenkins was configured using a simplified build approach, ensuring successful build execution.
________________________________________
## CI/CD Workflow
```
GitHub Push → GitHub Actions → Test → Docker Build → Jenkins Build
```
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
Muruganantham K

Master’s in Software Engineering, BITS Pilani
