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
        stage('Build project') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Execute tests') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
