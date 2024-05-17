pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                build_docker_image()
            }
        }
        stage('deploy-dev') {
            steps {
                deploy("DEV")
            }
        }
        stage('api-test-dev') {
            steps {
                run_api_tests("DEV")
            }
        }
        stage('deploy-stg') {
            steps {
                deploy("STG")
            }
        }
        stage('api-test-stg') {
            steps {
                run_api_tests("STG")
            }
        }
        stage('deploy-prd') {
            steps {
                deploy("PRD")
            }
        }
        stage('api-test-prd') {
            steps {
                run_api_tests("PRD")
            }
        }
    }
}

def build_docker_image(){
    echo "Build sample-book-app.. "
    sh "docker build --no-cache -t jekaterina2021/sample-book-app ."

    echo "Running unit tests for node application in docker container.."
    sh "docker run --rm --entrypoint=npm jekaterina2021/sample-book-app run test"
    
    echo "Pushing docker image to docker registry.."
    sh "docker push jekaterina2021/sample-book-app"
}

def deploy(String environment){
    echo "Deployment triggered to ${environment} environment.. "
}

def run_api_tests(String environment){
    echo "API Tests against ${environment} environment.. "
}
