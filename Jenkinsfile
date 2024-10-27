pipeline {
    agent any
    stages {
        stage('Build .NET app') {
            steps {
                bat 'dotnet build'
            } 
        }
        stage('Run all tests') {
            steps {
                bat 'dotnet test'
            } 
        }
    }
}