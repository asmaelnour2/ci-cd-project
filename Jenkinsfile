pipeline {
    agent any

    stages {

        stage('Clean Workspace') {
            steps {
                deleteDir()
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/asmaelnour2/ci-cd-project.git'
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