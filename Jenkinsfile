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
                echo 'Testing the first module aggs-matrix-stats'
                sh 'gradle clean test --scan -p aggs-matrix-stats'

                echo 'Testing the second module lang-painless'
                sh 'gradle clean test --scan -p lang-painless'

                echo 'Testing the third module ingest-common'
                sh 'gradle clean test --scan -p ingest-common'

                echo 'Testing the fourth module lang-mustache'
                sh 'gradle clean test --scan -p lang-mustache'

                echo 'Testing the fifth module lang-expression'
                sh 'gradle clean test --scan -p lang-expression'
            }
        }
    }

    post {
        always {
            echo 'Pipeline status logs'
        }
        success {
            echo 'Pipeline build successed'
        }
        failure {
            echo 'Pipeline build failed. See console output for more informations'
        }
        unstable {
            echo 'Pipeline build was marked as unstable'
        }
        changed {
            echo 'Pipeline build status has changed from last run'
        }
    }
}