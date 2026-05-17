pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Vishwas1412/my-first-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t foodhub-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop foodhub-container || true'
                sh 'docker rm foodhub-container || true'
                sh 'docker run -d -p 80:80 --name foodhub-container foodhub-app'
            }
        }
    }
}