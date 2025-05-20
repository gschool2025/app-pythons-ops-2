pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'hello-world-app'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/gschool2025/app-pythons-ops-2.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("${env.DOCKER_IMAGE}:latest").run("-p 5000:5000")
                }
            }
        }
    }
}
