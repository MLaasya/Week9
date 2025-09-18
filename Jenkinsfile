pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 laasya88/registration:v1'
                bat 'docker push laasya88/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f E:\1286/deployment.yaml'
                bat 'kubectl apply -f E:\1286/service.yaml'
            }
        }
        
    }
}
