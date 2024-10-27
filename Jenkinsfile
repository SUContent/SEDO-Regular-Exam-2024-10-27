pipeline {
    agent any

    stages {
        stage('Check Branch') {
            steps {
                script {
                    echo "Current branch: ${env.GIT_BRANCH}"
                }
            }
        }
        
        stage('Install dependecies') {
            when {
                expression { env.GIT_BRANCH == 'origin/feature-ci-pipeline' }
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build .NET') {
            when {
                expression { env.GIT_BRANCH == 'origin/feature-ci-pipeline' }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Unit Tests') {
            when {
                expression { env.GIT_BRANCH == 'origin/feature-ci-pipeline' }
            }
            steps {
                bat 'dotnet test SoftUniBazar.Tests/SoftUniBazar.Tests.csproj --no-build --verbosity normal'
            }
        }
       stage('Run Integration Tests') {
            when {
                expression { env.GIT_BRANCH == 'origin/feature-ci-pipeline' }
            }
            steps {
                bat 'dotnet test SoftUniBazar.IntegrationTests/SoftUniBazar.IntegrationTests.csproj --no-build --verbosity normal'
            }
        }
    }
}
