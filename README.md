# DevOps CI/CD Projects

This repository contains two DevOps CI/CD tasks demonstrating automated application testing, building, and deployment using GitHub Actions, Jenkins, and Docker.

---

## Task 1: CI/CD Pipeline using GitHub Actions

### Objective

Automate the process of testing, building, and deploying a Node.js application using GitHub Actions and Docker.

### Tools Used

- GitHub
- GitHub Actions
- Node.js
- Docker
- Docker Hub

### Pipeline

```text
Code Push to Main
        ↓
GitHub Actions
        ↓
Install Dependencies
        ↓
Run Tests
        ↓
Build Docker Image
        ↓
Login to Docker Hub
        ↓
Push Docker Image
```

### Workflow

The GitHub Actions workflow is defined in:

```text
.github/workflows/main.yml
```

The pipeline is triggered when code is pushed to the `main` branch.

It performs the following steps:

1. Checks out the source code.
2. Installs Node.js dependencies.
3. Runs application tests.
4. Builds a Docker image.
5. Logs in to Docker Hub using GitHub Secrets.
6. Pushes the Docker image to Docker Hub.

---

## Task 2: Jenkins CI/CD Pipeline

### Objective

Create a Jenkins pipeline to automate the process of building, testing, and deploying the Node.js application.

### Tools Used

- Jenkins
- Docker
- GitHub
- Node.js
- npm

### Pipeline

```text
GitHub Repository
        ↓
Jenkins
        ↓
Checkout Code
        ↓
Install Dependencies
        ↓
Run Tests
        ↓
Build Docker Image
        ↓
Deploy Container
```

### Jenkinsfile

The Jenkins pipeline is defined in:

```text
Jenkinsfile
```

The pipeline contains the following stages:

1. **Checkout** – Retrieves the project source code from GitHub.
2. **Install Dependencies** – Installs project dependencies using `npm ci`.
3. **Test** – Runs the application tests using `npm test`.
4. **Build Docker Image** – Creates a Docker image for the Node.js application.
5. **Deploy** – Runs the Docker container and exposes the application on port `3000`.

### Jenkins Pipeline Result

The Jenkins pipeline was successfully executed and completed with a successful build.

---

## Project Structure

```text
nodejs-demo-app/
│
├── .github/
│   └── workflows/
│       └── main.yml
│
├── test/
│   └── app.test.js
│
├── app.js
├── Dockerfile
├── Jenkinsfile
├── package.json
├── package-lock.json
└── README.md
```

## Application

This project uses a simple Node.js application to demonstrate CI/CD automation.

The application is containerized using Docker and can be deployed as a Docker container.

## Conclusion

These tasks demonstrate how CI/CD pipelines can automate the software delivery process by integrating:

- Source code management with GitHub
- Automated testing
- Docker image creation
- Docker-based deployment
- GitHub Actions automation
- Jenkins pipeline automation
