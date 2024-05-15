pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                script{
                    build_docker_image()
                }
            }
        }
        stage('deploy-dev') {
            steps {
                script{
                    deploy("DEV")
                }
            }
        }
        stage('api-test-dev') {
            steps {
                script{
                    run_api_tests("DEV")
                }
            }
        }
        stage('deploy-stg') {
            steps {
                script{
                    deploy("STG")
                }
            }
        }
        stage('api-test-stg') {
            steps {
                script{
                    run_api_tests("STG")
                }
            }
        }
        stage('deploy-prd') {
            steps {
                script{
                    deploy("PRD")
                }
            }
        }
        stage('api-test-prd') {
            steps {
                script{
                    run_api_tests("PRD")
                }
            }
        }
    }
}

def build_docker_image(){
    echo "Build sample-book-app.. "
}

def deploy(String environment){
    echo "Deployment triggered to ${environment} environment.. "
}

def run_api_tests(String environment){
    echo "API Tests against ${environment} environment.. "
}