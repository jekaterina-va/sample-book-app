pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                scripts{
                    build_docker_image()
                }
            }
        }
        stage('deploy-dev') {
            steps {
                scripts{
                    deploy("DEV")
                }
            }
        }
        stage('api-test-dev') {
            steps {
                scripts{
                    run_api_tests("DEV")
                }
            }
        }
        stage('deploy-stg') {
            steps {
                scripts{
                    deploy("STG")
                }
            }
        }
        stage('api-test-stg') {
            steps {
                scripts{
                    run_api_tests("STG")
                }
            }
        }
        stage('deploy-prd') {
            steps {
                scripts{
                    deploy("PRD")
                }
            }
        }
        stage('api-test-prd') {
            steps {
                scripts{
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