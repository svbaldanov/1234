pipeline {
  agent any
  stages {
    stage('buzz build') {
      steps {
        script {
          def buildScriptPath = "/var/lib/jenkins/workspace/12345_main/build.sh"
        }

      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            script {
              def buildScriptPath = "/var/lib/jenkins/workspace/12345_main/test.sh"
            }

          }
        }

        stage('testB') {
          steps {
            sh '''sleep 10
echo done'''
          }
        }

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