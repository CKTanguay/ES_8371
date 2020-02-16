pipeline {
    agent any

    stages {
        stage ('Build stage') {
            steps {
                sh './gradlew assemble'
            }
        }
    }
}