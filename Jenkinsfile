pipeline {
    agent any

    environment {
        dockerhubUsername = 'turadmin'
        dockerhubPassword = '75458811qQ'
    }

    stages {
        stage('Build and Push Docker Image') {
            steps {
                sh '''
                    # Сборка Docker-образа
                    docker build -t turadmin/devops:job1 .

                    # Вход в Docker Hub с использованием заданных данных
                    echo "$dockerhubPassword" | docker login -u "$dockerhubUsername" --password-stdin

                    # Выгрузка Docker-образа в Docker Hub
                    docker push turadmin/devops:job1
                '''
            }
        }
    }
}
