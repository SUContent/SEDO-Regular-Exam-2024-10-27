pipeline {
    agent any
    stages {
        stage('1. Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('2. Dotnet Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('3. Execute All Tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}