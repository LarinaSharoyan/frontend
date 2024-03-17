pipeline {
  agent any
  environment {
    DOCKER_HUB_CREDENTIALS = credentials('docker-pat')
  }
  stages {
    stage('Build and Push Image') {
      steps {
        echo env.DOCKER_HUB_CREDENTIALS
        script {
          withCredentials([usernamePassword(credentialsId: 'docker-pat', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
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
