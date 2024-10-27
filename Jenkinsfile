pipeline {
    agent any 
           
    stages {   
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

         stage('.Net Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run all tests') {
            steps {
                 bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
