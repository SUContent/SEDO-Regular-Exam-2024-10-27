pipeline {
    agent any 
    stages {
        stage('Restore DotNet dependencies') { 
            steps {
                bat 'dotnet restore' 
            }
        }
        stage('DotNet Build project') { 
            steps {
                bat 'dotnet build --no-restore' 
            }
        }
        stage('Execute all tests') { 
            steps {
                bat 'dotnet test --no-build --verbosity normal' 
            }
        }
    }
}
