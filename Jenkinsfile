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