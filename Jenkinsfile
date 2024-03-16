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
            docker.build("front").push("docker.io/parandzem/front:latest")
          }
        }
      }
    }
  }
}
