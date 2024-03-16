pipeline {
    agent any

    stages {
        stage('Build and Push Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: docker, usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    script {
                        docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                            docker.build("frontend")
                            docker.image("frontend").push("latest")
                        }
                    }
                }
            }
        }
    }
}
