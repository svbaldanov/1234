pipeline {
  agent any
  stages {
    stage('buzz build') {
      steps {
        sh 'print 1'
      }
    }

    stage('test') {
      steps {
        sh 'print 2'
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