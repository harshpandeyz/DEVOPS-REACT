pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/harshpandeyz/DEVOPS-REACT.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t gamehub .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop gamehub-app || true'
                sh 'docker rm gamehub-app || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name gamehub-app gamehub'
            }
        }
    }
}
