pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t foodhub .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker stop foodhub-container || exit 0'
                bat 'docker rm foodhub-container || exit 0'
                bat 'docker run -d -p 8080:80 --name foodhub-container foodhub'
            }
        }
    }
}