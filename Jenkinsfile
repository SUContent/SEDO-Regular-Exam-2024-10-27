pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:$PATH"
    }

    stages {
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
        stage('Execute tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
