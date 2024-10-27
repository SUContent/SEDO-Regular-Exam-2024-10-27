pipeline {
    agent any 
    stages {
        stage('Dotnet Build') { 
            steps {
                bat 'dotnet build' 
            }
        }
        stage('Execute tests') { 
            steps {
                bat 'dotnet test' 
            }
        }
    }
}
