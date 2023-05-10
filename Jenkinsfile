pipeline {
  agent any
  
  stages {
    stage('Deployment Development')  
		CLIENT_ID = credentials('connectedAppClientId')
        CLIENT_SECRET = credentials('connectedAppClientSecret')
    stage('Build and deploy') {
      steps {
        bat 'mvn clean deploy -DmuleDeploy -Danypoint.platform.client_id=%CLIENT_ID% -Danypoint.platform.client_secret=%CLIENT_SECRET%'
      }
    }
  }
}
