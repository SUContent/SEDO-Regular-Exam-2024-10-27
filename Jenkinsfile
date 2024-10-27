pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/enevmartin/SEDO-Regular-Exam-2024-10-27.git', branch: 'feature-ci-pipeline'
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
