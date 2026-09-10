pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/anjalipanagar/jenkins-node-app.git'
            }
        }
        stage ('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage ('Run App') {
            steps {
                bat 'node index.js'
            }
        }
        stage ('Test App') {
            steps {
                bat 'npm test'
            }
        }
        stage ('Build Docker Image') {
            steps {
                bat 'docker build -t jenkins-node-app .'
            }
        }
        stage ('Run Docker Container') {
            steps {
                bat 'docker run -d -p 3000:3000 --name node-add-container jenkins-node-app'
            }
        }
        stage ('Docker Container Logs') {
            steps {
                bat 'docker logs node-add-container'
            }
        }
    }
}