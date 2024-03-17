pipeline {
  agent any
  stages {
    stage('Build and Push Image') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'parandzem', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
          script {
            docker.build("parandzem/front")
            docker.image("parandzem/front").push("latest")
          }
        }
      }
    }
  }
}
