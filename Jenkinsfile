pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                cleanWs()
            }
        }

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/asmaelnour2/ci-cd-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop my-site || true
                docker rm my-site || true
                docker run -d -p 8085:80 --name my-site my-website
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished execution successfully.'
        }
    }
}