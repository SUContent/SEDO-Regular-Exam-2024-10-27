pipeline {
    agent any

    stages {
       stage('Checkout') {
            steps {
                git credentialsId: 'GitHubToken', url: 'https://github.com/caaeesar/SEDO-Regular-Exam-2024-10-27'
            }
         }
        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
         stage('Build project') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Execute test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
