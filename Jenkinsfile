pipeline {
    agent any

    stages {
        stage ('Build stage') {
            steps {
                echo 'Building the project'
                echo './gradlew --continue clean build --scan -s -p modules/'
            }
        }

        stage ('Linter') {
            steps {
                echo 'Validating code quality'
                echo './gradlew lint'
            }
        }

        stage ('Testing') {
            steps {
                echo 'Testing the first module aggs-matrix-stats'
                echo 'gradle clean test --scan -p aggs-matrix-stats'

                echo 'Testing the second module lang-painless'
                echo 'gradle clean test --scan -p lang-painless'

                echo 'Testing the third module ingest-common'
                echo 'gradle clean test --scan -p ingest-common'

                echo 'Testing the fourth module lang-mustache'
                echo 'gradle clean test --scan -p lang-mustache'

                echo 'Testing the fifth module lang-expression'
                echo 'gradle clean test --scan -p lang-expression'
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