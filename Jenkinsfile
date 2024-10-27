pipeline {
  agent any
  stages {
    stage('Restore Dependencies') {
      steps {
        bat 'dotnet restore'
      }
    }
    stage('Build Project') {
      steps {
        bat 'dotnet build --no-restore'
      }
    }
    stage('Execute Test') {
      steps {
        bat 'dotnet test --no-build --verbosity normal'
      }
    }
  }
}
