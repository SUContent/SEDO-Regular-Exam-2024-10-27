pipeline {
    agent any
    when {
        branch 'feature-ci-pipeline' 
    }
    stages {
        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'dotnet test --no-build --configuration Release'
            }
        }
    }
}
