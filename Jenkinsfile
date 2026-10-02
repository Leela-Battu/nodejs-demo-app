pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm ci'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat '"C:\\Users\\leela\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t nodejs-demo-app .'
            }
        }

        stage('Deploy') {
            steps {
                bat '"C:\\Users\\leela\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" rm -f nodejs-demo-container || exit 0'
                bat '"C:\\Users\\leela\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" run -d --name nodejs-demo-container -p 3000:3000 nodejs-demo-app'
            }
        }
    }
}