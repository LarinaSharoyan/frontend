pipeline {
  agent any
  stages {
    stage('Build and Push Image') {
      steps {
        script {
          withCredentials([usernamePassword(credentialsId: 'parandzem', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
            docker.withRegistry('https://hub.docker.com') {
              docker.build("parandzem/front")
              docker.image("parandzem/front").push()
            }
          }
        }
      }
    }
  }
}
