pipeline {
    agent any

    stages {
        stage ('Build stage') {
            steps {
                sh './gradlew run'
            }
        }

        stage ('Linter') {
            steps {
                echo 'This is the linting stage'
            }
        }

        stage ('Testing') {
            steps {
                echo 'This is the testing stage'
            }
        }
    }
}