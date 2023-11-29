pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo '12345'
        sh 'echo Another Placeholder'
      }
    }

    stage('test') {
      steps {
        sleep 5
        sh 'echo Success!'
      }
    }

    stage('deploy') {
      steps {
        echo 'Placeholder1'
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