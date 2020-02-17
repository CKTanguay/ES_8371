pipeline {
    agent any

    stages {
        stage ('Build stage') {
            steps {
                echo './gradlew run'
            }
        }

        stage ('Linter') {
            steps {
                echo 'This is the linting stage'
                sh 'gradlew lint'
            }
        }

        stage ('Testing') {
            steps {
                echo 'This is the testing stage'
            }
        }
    }
}