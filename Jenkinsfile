pipeline {
  agent any
  
  stages {
	stage('Build and deploy') {
		
	 CLIENT_ID = credentials('connectedAppClientId')
         CLIENT_SECRET = credentials('connectedAppClientSecret')
         steps {
        bat 'mvn clean deploy -DmuleDeploy -Danypoint.platform.client_id=%CLIENT_ID% -Danypoint.platform.client_secret=%CLIENT_SECRET%'
      }
    }
  }
}
