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
      archiveArtifacts 'target/*.jar'
      stash(name: 'Java 11', includes: 'target/**')
    }

    failure {
      echo 'Build or deployment failed!'
    }

  }
}