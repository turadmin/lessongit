pipeline {
    agent any
    
    environment {
        DOCKER_REGISTRY = "https://registry.hub.docker.com"
        DOCKER_CREDENTIALS = "turadmin"
    }
    
    stages {
        stage('Build and Push Docker Image') {
            steps {
                script {
                    docker.withRegistry(DOCKER_REGISTRY, DOCKER_CREDENTIALS) {
                        def customImage = docker.build("turadmin/devops:job1")
                        customImage.push()
                    }
                }
            }
        }
    }
}
