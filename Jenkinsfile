pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'prashil09/image-service:1.0'
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/bluishhh/204-206-211-239-ECommerceMicroservises.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE ./image-service/'
            }
        }
        stage('Test') {
            steps {
                // Define steps for running your tests here
                sh 'echo "Running tests in Image Service"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f ./image-service/k8s/deployment.yaml'
                sh 'kubectl apply -f ./image-service/k8s/service.yaml'
            }
        }
    }
}
