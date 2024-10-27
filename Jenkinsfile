
pipeline {
    agent any

    stages {
        stage('Restore dependancies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build Project') {
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
