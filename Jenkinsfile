pipeline {
  agent any
  
  environment {
    ANYPOINT_CLIENT_ID = credentials('connectedAppClientId')
    ANYPOINT_CLIENT_SECRET = credentials('connectedAppClientSecret')
  }
  
  stages {
    stage('Build') {
      steps {
        bat 'mvn -U -V -e -B -DskipTests package'
      }
    }
    
    stage('Deploy') {
      steps {
        withCredentials([string(credentialsId: 'connectedAppClientId', variable: 'ANYPPOINT_CLIENT_ID'),
                          string(credentialsId: 'connectedAppClientSecret', variable: 'ANYPPOINT_CLIENT_SECRET')]) {
          bat 'mvn -U -V -e -B -DskipTests deploy -PDevelopment -DmuleDeploy -Danypoint.platform.client_id=${ANYPPOINT_CLIENT_ID} -Danypoint.platform.client_secret=${ANYPPOINT_CLIENT_SECRET}'
        }
      }
    }
  }
}
