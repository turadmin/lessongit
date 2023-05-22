pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker build -t turadmin/devops:job1 .
            }
        }
        stage('Push') {
            steps {
                docker push turadmin/devops:job1 .
            }
        }
    }
}