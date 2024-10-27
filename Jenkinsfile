pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Restore Dependencies') {
            steps {
                script {
                    sh 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'dotnet build --no-restore'
                }
            }
        }

        stage('Run All Tests') {
            steps {
                script {
                    sh 'dotnet test --no-build --verbosity normal'
                }
            }
        }
    }
}
