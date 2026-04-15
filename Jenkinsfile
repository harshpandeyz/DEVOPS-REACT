pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/harshpandeyz/DEVOPS-REACT.git'
            }
        }

        stage('Install') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t gamehub .'
            }
        }
    }
}
