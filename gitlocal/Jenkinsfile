pipeline {
    agent any
    
    environment {
        // Указываем переменные среды, если необходимо
        MAVEN_HOME = tool 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                // Получаем исходный код из репозитория
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Вызываем Maven для сборки проекта
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }

        stage('Test') {
            steps {
                // Выполняем тестирование (здесь может быть вызов тестового фреймворка)
                sh "${MAVEN_HOME}/bin/mvn test"
            }
        }

        stage('Deploy') {
            steps {
                // Развертываем приложение, например, на сервер
                sh 'deploy-script.sh'
            }
        }
    }

    post {
        // Определяем действия, которые нужно выполнить после завершения пайплайна
        success {
            // Действия при успешном завершении
            echo 'Build and deployment succeeded!'

            // Можно добавить дополнительные действия
        }
        failure {
            // Действия при ошибке
            echo 'Build or deployment failed!'

            // Можно добавить дополнительные действия
        }
    }
}
