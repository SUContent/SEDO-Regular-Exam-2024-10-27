pipeline {
    agent any

    environment {
        TARGET_BRANCH = 'feature-ci-pipeline'
    }
    stages {
        stage('Restore Dependencies') { 
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {

            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
