pipeline {
  agent any

  stages {
    stage('Restore dependencies') {
      steps {
        bat 'dotnet restore'
      }
    }

    stage('Build application') {
      steps {
        bat 'dotnet build --no-restore'
      }
    }
      
    stage('Test application') {
      steps {
        bat 'dotnet test --no-build --verbosity normal'
      }
    }
  }
}
