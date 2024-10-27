pipeline {
    agent any
    triggers {
        pollSCM('H/5 * * * *')
    }
    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build dotnet app') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run unit tests') {
            steps {
                bat 'dotnet test SoftUniBazar.Tests\SoftUniBazar.Tests.csproj --no-build --verbosity normal'
            }
        }
        stage('Run integration tests') {
            steps {
                bat 'dotnet test SoftUniBazar.IntegrationTests/SoftUniBazar.IntegrationTests.csproj --no-build --verbosity normal'
            }
        }
    }
}
