pipeline {
  agent {
    docker {
      image 'mcr.microsoft.com/dotnet/sdk:6.0'
      args  '-u root:root' // sometimes needed for permissions
    }
  }

  stages {
    stage('Restore') { steps { sh 'dotnet restore' } }
    stage('Build')   { steps { sh 'dotnet build -c Release --no-restore' } }
    stage('Test')    { steps { sh 'dotnet test -c Release --no-build' } }
  }
}
