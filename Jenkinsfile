pipeline {
  agent {
    docker { image 'mcr.microsoft.com/dotnet/sdk:6.0' }
  }

  triggers { githubPush() }

  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Restore')  { steps { sh 'dotnet restore' } }
    stage('Build')    { steps { sh 'dotnet build --no-restore' } }
    stage('Test')     { steps { sh 'dotnet test --no-build --verbosity normal' } }
  }
}
