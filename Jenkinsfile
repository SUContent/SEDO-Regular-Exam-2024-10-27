pipeline {
    agent any

    stages {
        stage('Install dependecies') {
            when {
                  branch 'feature-ci-pipeline'  
              }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build .NET') {
            when {
                    branch 'feature-ci-pipeline'  
                }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Unit Tests') {
            when {
                    branch 'feature-ci-pipeline'  
                }
            steps {
                bat 'dotnet test SEDO-Regular-Exam-2024-10-27/SoftUniBazar.Data\SoftUniBazar.Data.csproj --no-build --verbosity normal
            }
        }
       stage('Run Integration Tests') {
            when {
                    branch 'feature-ci-pipeline'  
                }
            steps {
                bat 'dotnet test SoftUniBazar.IntegrationTests/SoftUniBazar.IntegrationTests.csproj --no-build --verbosity normal
            }
        }
    }
}
