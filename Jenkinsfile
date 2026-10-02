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
                bat 'docker build -t nodejs-demo-app .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker rm -f nodejs-demo-container || exit 0'
                bat 'docker run -d --name nodejs-demo-container -p 3000:3000 nodejs-demo-app'
            }
        }
    }
}