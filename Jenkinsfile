pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/julie249/DevOps-App.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker stop devops-container || exit 0'
                bat 'docker rm devops-container || exit 0'
                bat 'docker run -d -p 3000:3000 --name devops-container devops-app'
            }
        }
    }
}