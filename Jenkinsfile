pipeline {
  agent any
  stages {
    stage('Build and Push Image') {
      steps {
        script {
          withCredentials([usernamePassword(credentialsId: 'parandzem', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
            docker.withRegistry('https://index.docker.io/v1/') {
              def customImage = docker.build("parandzem/front")
              customImage.push()
            }
          }
        }
      }
    }
  }
}
