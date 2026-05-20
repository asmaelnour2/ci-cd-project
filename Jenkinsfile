pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/asmaelnour2/ci-cd-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "No tests yet - pass stage"'
            }
        }

        stage('Deploy') {
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