pipeline {
    agent any
    
    tools {
        // Использовать инструмент Maven, установленный из репозитория
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                // Вызов команд Maven без указания полного пути
                sh 'mvn clean package'
            }
        }
        // Другие этапы вашего пайплайна
    }

    // Обработка успешного или неуспешного завершения пайплайна
    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}
