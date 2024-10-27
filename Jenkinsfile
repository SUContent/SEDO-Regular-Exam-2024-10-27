pipeline {
    agent any 

  stages {
    
    stage('Restore Dependencies') {
     steps {
          bat 'dotnet restore'
            }
        }
    stage('Dotnet Build') { 
     steps {
          bat 'dotnet build --no-restore' 
            }
        }
    stage('Ececute Unit and Integration Tests') { 
        steps {
          bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
