pipeline {
    agent any

    stages {
        stage('Restore Dependencies') {
            when {
                branch 'feature-ci-pipeline' 
            }       
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            when {
                branch 'feature-ci-pipeline' 
            }
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            when {
                branch 'feature-ci-pipeline' 
            }
            steps {
                sh 'dotnet test --no-build --configuration Release'
            }
        }
    }
}
