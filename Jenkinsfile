pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/asmaelnour2/ci-cd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8080:80 my-website'
            }
        }
    }
}