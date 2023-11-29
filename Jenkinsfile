pipeline {
  agent any
  stages {
    stage('buzz build') {
      steps {
        sh './jenkins/build.sh'
      }
    }

    stage('test') {
      steps {
        sh './jenkins/test-all.sh'
      }
    }

  }
  tools {
    maven '395'
  }
  post {
    success {
      echo 'Build and deployment succeeded!'
    }

    failure {
      echo 'Build or deployment failed!'
    }

  }
}