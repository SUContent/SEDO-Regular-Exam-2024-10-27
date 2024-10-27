pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build the project') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute the tests') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
