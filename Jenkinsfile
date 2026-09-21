pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-html-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop my-html-container || true'
                sh 'docker rm my-html-container || true'
                sh 'docker run -d --name my-html-container -p 8082:80 my-html-app'
            }
        }
    }
}
