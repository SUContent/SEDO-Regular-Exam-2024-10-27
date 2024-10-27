pipeline {
    agent any

    environment {
        TARGET_BRANCH = 'feature-ci-pipeline'
    }

    stages {
        stage('Restore Dependencies') { 
            when {
                expression { env.BRANCH_NAME == env.TARGET_BRANCH }
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            when {
                expression { env.BRANCH_NAME == env.TARGET_BRANCH }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            when {
                expression { env.BRANCH_NAME == env.TARGET_BRANCH }
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
