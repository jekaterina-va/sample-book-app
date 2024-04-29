pipeline {
    agent any
    parameters{
        string(name: 'NAME', defaultValue: 'World', description: 'Who we should greet?')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh docker --version
            }
        }
    }
}