pipeline {
  agent any
  
  environment {
    CLIENT_ID = credentials('connectedAppClientId')
    CLIENT_SECRET = credentials('connectedAppClientSecret')
  }
  
  stages {
    stage('Build and deploy') {
      steps {
        withCredentials([string(credentialsId: 'connectedAppClientId', variable: 'CLIENT_ID'),
                         string(credentialsId: 'connectedAppClientSecret', variable: 'CLIENT_SECRET')]) {
          bat "mvn clean deploy -DmuleDeploy -Danypoint.platform.client_id=${CLIENT_ID} -Danypoint.platform.client_secret=${CLIENT_SECRET}"
        }
      }
    }
  }
}
