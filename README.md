# 🚀 CI/CD Pipeline Project (Docker + Jenkins)

This project demonstrates a complete CI/CD pipeline using a simple static website deployed with Docker and automated using Jenkins.

## 📌 Project Overview

The goal of this project is to automate the process of pulling code from GitHub, building a Docker image, running the application inside a container, and automating the workflow using Jenkins Pipeline.

## 🧰 Technologies Used

HTML, CSS (Frontend Template), Docker, Jenkins, Git, GitHub.

## 📁 Project Structure

startbootstrap-agency/
index.html
css/
js/
assets/
Dockerfile
README.md

## 🐳 Docker Setup

Build Docker Image:
docker build -t my-website .

Run Docker Container:
docker run -d -p 8080:80 my-website

Then open:
http://localhost:8080

## 🔄 CI/CD Pipeline (Jenkins)

The pipeline performs the following stages:
1. Clone repository from GitHub  
2. Build Docker image  
3. Run Docker container  

## ⚙️ Jenkins Pipeline Flow

GitHub → Jenkins → Docker Build → Deploy Container

## 🧪 Jenkins Pipeline Script

pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Build Image') {
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

## 🎯 Project Outcome

After running the pipeline successfully, the website is automatically deployed, no manual build or run is required, and full CI/CD automation is achieved.

## 📸 Screenshots

Application UI, Jenkins Pipeline Success, GitHub Repository.

## 👩‍💻 Author

Asma Aboelnour

## 🚀 Notes

This project is a basic DevOps CI/CD demonstration using Docker and Jenkins for automation.
