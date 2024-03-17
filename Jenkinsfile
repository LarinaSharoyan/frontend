pipeline {
  agent any
  stages {
    stage('Build and Push Image') {
      steps {
        echo env.DOCKER_HUB_CREDENTIALS
        script {
          docker.withRegistry('https://index.docker.io/v1/', 'docker-pat') {
            docker.build("parandzem/front")
            docker.image("parandzem/front").push()
          }
        }
      }
    }
  }
}
