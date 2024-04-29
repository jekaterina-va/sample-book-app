pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                echo "Build sample-book-app.. "
            }
        }
        stage('deploy-dev') {
            steps {
                echo "Deployment triggered to DEV environment.. "
            }
        }
        stage('api-test-dev') {
            steps {
                echo "API Tests against DEV environment.. "
            }
        }
        stage('deploy-stg') {
            steps {
                echo "Deployment triggered to STG environment.. "
            }
        }
        stage('api-test-stg') {
            steps {
                echo "API Tests against STG environment.. "
            }
        }
        stage('deploy-prd') {
            steps {
                echo "Deployment triggered to PRD environment.. "
            }
        }
        stage('api-test-prd') {
            steps {
                echo "API Tests against PRD environment.. "
            }
        }
    }
}