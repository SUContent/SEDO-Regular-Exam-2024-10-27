pipeline {
    agent any

    // Restrict pipeline to run only on 'feature-ci-pipeline' branch
    triggers {
        pollSCM('* * * * *') // Optional: to poll Git for changes
    }
    
    stages {
        stage('Restore Dependencies') { 
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Tests') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
