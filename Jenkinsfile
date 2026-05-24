pipeline {

    agent any

    stages {
	stage('Clone Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Lahari268/day49-cicd.git'
    }
}
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t laharikalva/kravix-app:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker push laharikalva/kravix-app:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
            }
        }
    }
}