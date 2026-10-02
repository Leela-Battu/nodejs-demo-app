-> Node.js CI/CD Pipeline

-> Overview

This project demonstrates a CI/CD pipeline for a Node.js application using GitHub Actions and Docker.

Whenever code is pushed to the `main` branch, GitHub Actions automatically:

- Installs dependencies
- Runs tests
- Builds a Docker image
- Pushes the image to Docker Hub

-> Technologies:

- Node.js
- Express.js
- Jest
- Docker
- GitHub Actions
- Docker Hub

-> CI/CD Flow:

Git Push
   ↓
GitHub Actions
   ↓
Install & Test
   ↓
Docker Build
   ↓
Docker Hub

Run Locally
npm install
npm start

Open:
http://localhost:3000


Docker:
- docker build -t nodejs-demo-app .
- docker run -p 3000:3000 nodejs-demo-app
