pipeline {
    agent any

    stages {
        stage ('Build stage') {
            steps {
                echo 'test'
            }

            steps {
                sh './gradlew assemble'
            }
        }
    }
}