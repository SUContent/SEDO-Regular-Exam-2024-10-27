pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Execute Unit Tests') {
            steps {
                bat 'dotnet test SoftUniBazar.Tests/SoftUniBazar.Tests.csproj --no-build --verbosity normal'
            }
            post {
                success {
                    echo 'Unit tests passed, proceeding to integration tests.'
                }
                failure {
                    echo 'Unit tests failed, skipping integration tests.'
                }
            }
        }

        stage('Execute Integration Tests') {
            when {
                expression { currentBuild.result == null || currentBuild.result == 'SUCCESS' }
            }
            steps {
                bat 'dotnet test SoftUniBazar.IntegrationTests/SoftUniBazar.IntegrationTests.csproj --no-build --verbosity normal'
            }
        }
    }
}
