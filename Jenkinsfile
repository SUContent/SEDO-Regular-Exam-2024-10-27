pipeline {
    agent any

    stages {
        stage('Restore Dependencies') {
            when {
                expression { env.BRANCH_NAME == 'feature-ci-pipeline' } 
            }       
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            when {
                expression { env.BRANCH_NAME == 'feature-ci-pipeline' } 
            }
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            when {
                expression { env.BRANCH_NAME == 'feature-ci-pipeline' } 
            }
            steps {
                sh 'dotnet test --no-build --configuration Release'
            }
        }
    }
}
