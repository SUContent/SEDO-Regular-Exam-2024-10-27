pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'feature-ci-pipeline'
            }
        }
        stage('Build') {
            steps {
                script {
                    echo 'Building the application...'
                    sh 'dotnet build --configuration Release'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh 'dotnet test --no-build --configuration Release'
                }
            }
        }
    }
}
