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
    }
}