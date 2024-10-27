pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Dotnet Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal '
            }
        }
    }
}
