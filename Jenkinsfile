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
                echo 'gradlew lint'
            }
        }

        stage ('Testing') {
            steps {
                sh '''
                    echo "Testing the first module aggs-matrix-stats"
                    ls
                '''
            }
        }
    }
}