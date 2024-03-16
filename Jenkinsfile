pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('docker')
    }

    stages {
        stage('Build and Push Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: DOCKER_HUB_CREDENTIALS, usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    script {
                        docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                            docker.build("front")
                            docker.image("front").push("latest")
                        }
                    }
                }
            }
        }
    }
}
