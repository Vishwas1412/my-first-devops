pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t foodhub-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop foodhub-container || true'
                sh 'docker rm foodhub-container || true'
                sh 'docker run -d -p 8081:80 --name foodhub-container foodhub-app'
            }
        }
    }
}