pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
        echo '12345'
      }
    }

    stage('test') {
      steps {
        echo 'Placeholder'
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