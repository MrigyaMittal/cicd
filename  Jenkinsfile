pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building Docker image'
                sh 'docker build -t hello-cicd:latest .'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to Kubernetes'
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}