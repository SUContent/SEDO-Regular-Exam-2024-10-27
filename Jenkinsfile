pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute All Tests') {
            steps{
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
