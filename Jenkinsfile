pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build the project') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run all tests') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}

