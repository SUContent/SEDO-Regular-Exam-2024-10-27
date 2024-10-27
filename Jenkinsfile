pipeline {
    agent any
    stages {
        stage('Restore dependecies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Dotnet Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute all tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
