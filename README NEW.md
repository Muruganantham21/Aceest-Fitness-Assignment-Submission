# ACEest-Fitness – DevOps CI/CD Project
## Project Overview
 
ACEest-Fitness App is a Flask-based web application designed for managing gym operations efficiently. It tracks members, workouts, and general gym management tasks. This application is developed to demonstrate a complete DevOps lifecycle. This project showcases modern DevOps practices including version control, automated testing, containerization, CI/CD pipelines, code quality analysis, multiple deployment strategies, and cloud deployment.
 
## Objectives
* Develop a functional Flask-based gym management system
* Implement version control using Git & GitHub
* Automate testing using Pytest
* Containerize the application using Docker
* Build CI/CD pipelines using GitHub Actions and Jenkins
* Perform static code analysis using SonarQube
* Implement multiple deployment strategies
* Deploy application on Kubernetes
* Deploy application on cloud platform
 
## Tech Stack
| Category |    Tools |
|----------|--------|
| Backend   | Python, Flask|
| Testing   | Pytest|
| Version Control   | Git, GitHub|
| CI/CD | GitHub Actions, Jenkins|
| Containerization  | Docker|
| Code Quality  | SonarQube|
| Orchestration | Kubernetes|
| Cloud Platform    | Render|
| Registry  | Docker Hub|
 
## Project Structure
```
aceest-fitness/
│── app.py
│── requirements.txt
│── Dockerfile
│── Jenkinsfile
│── sonar-project.properties
│── test_app.py
│
├── legacy_versions/
├── k8s/
│   ├── rolling/
│   ├── blue-green/
│   ├── canary/
│   ├── shadow/
│   ├── ab-testing/
│
└── .github/workflows/main.yml
```
 
## Local Setup
```bash
git clone https://github.com/Muruganantham21/Aceest-Fitness-Assignment-Submission
cd aceest-fitness
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python app.py
```
### Access:
```bash
http://127.0.0.1:5000
```
```bash
Default Login:
 
Username: admin
Password: admin
```
### Running Tests
```bash
pytest -v test_app.py
```
### Docker Usage
#### Build image:
```bash
docker build -t aceest-fitness .
```
#### Run container:
```bash
docker run -p 5000:5000 aceest-fitness
```
#### Docker Hub Images
```bash
muruganantham21/aceest-fitness:v1.0
muruganantham21/aceest-fitness:v2.0
muruganantham21/aceest-fitness:v3.0
muruganantham21/aceest-fitness:v3.2.4
muruganantham21/aceest-fitness:latest
```
## CI/CD Pipeline
### GitHub Actions
 
Triggered on every push:
 
* Checkout Code
* Install Dependencies
* Run Pytest
* Build Docker Image
 
### Jenkins
 
Used for build validation:
 
* Source Checkout
* Build Validation
* Test Stage
* SonarQube Stage
* Build Completion
 
### SonarQube Integration
* Static code analysis performed
* Identifies bugs, vulnerabilities, code smells
* Ensures maintainability
### Kubernetes Deployment
 
#### Deploy application:
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```
#### Check:
```bash
kubectl get pods
kubectl get svc
```
## Deployment Strategies Implemented
### 1. Rolling Update
```bash
kubectl set image deployment/aceest-fitness aceest-fitness=muruganantham21/aceest-fitness:latest
```
**Zero downtime upgrade**
 
### 2. Blue-Green Deployment
* Two environments: Blue (current), Green (new)
* Traffic switched via service selector
 
**Instant rollback capability**
 
### 3. Canary Deployment
* Stable + Canary deployments
* Traffic split using replica distribution
 
**Gradual rollout**
 
### 4. A/B Testing ✅
#### Application-Level:
* Flask randomly serves two UI versions
#### Kubernetes-Level:
* Separate deployments for Version A & B
 
**User experience comparison**
 
### 5. Shadow Deployment ✅
* New version deployed but not exposed
* Used for testing without impacting users
 
**Safe validation**
 
## Cloud Deployment
 
Application deployed using container image on cloud platform:
 
* Platform: Render
* Deployment Method: Docker Image
* Public URL available
 

## Architecture Flow
```text
Developer → GitHub → GitHub Actions → Docker Hub → Cloud (Render)
                                     → Kubernetes (Local)
                                     → Jenkins (Build Validation)
                                     → SonarQube (Code Quality)
```
## Key Learning Outcomes
* End-to-end CI/CD pipeline implementation
* Docker containerization and versioning
* Jenkins pipeline integration
* SonarQube static analysis
* Kubernetes orchestration
* Rolling updates and deployment strategies
* Cloud deployment fundamentals
* Real-world DevOps workflow

## Author
 
Muruganantham K

M.Tech Software Engineering
