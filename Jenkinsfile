pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    def dockerImage = docker.build('turadmin/devops:job1')
                    docker.withRegistry('https://registry.hub.docker.com', 'turadmin') {
                        dockerImage.push()
                    }
                }
            }
        }
    }
    
    post {
        always {
            script {
                docker.image('turadmin/devops:job1').withRegistry {
                    dockerImage.remove()
                }
            }
        }
    }
}
