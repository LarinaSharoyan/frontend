pipeline {
  agent any

  stages {
    stage('Build and Push Image') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'parandzem', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
          script {
            docker.build("front")
            docker.image("front").push("parandzem/front:latest")
          }
        }
      }
    }
  }
}
