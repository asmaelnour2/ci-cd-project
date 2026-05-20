pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm
            }
        }

        stage('Clone') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', url: 'https://github.com/asmaelnour2/ci-cd-project.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t my-website .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "No real tests yet"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying container...'
                sh '''
                docker stop my-site || true
                docker rm my-site || true
                docker run -d -p 8080:80 --name my-site my-website
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline Success'
        }

        failure {
            echo 'Pipeline Failed'
        }

        always {
            echo 'Cleaning up workspace...'
            deleteDir()
        }
    }
}