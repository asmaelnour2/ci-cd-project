pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop my-site || true
                docker rm my-site || true
                docker run -d -p 8080:80 --name my-site my-website
                '''
            }
        }
    }
}