pipeline {

  agent any
         
  stages {
    stage('Build and Deploy') {
      steps {
          echo  'hello world Munit test case'
      }
    }

     stage('Deployment Development')      {
         
         environment {
        CLIENT_ID = credentials('connectedAppClientId')
        CLIENT_SECRET = credentials('connectedAppClientSecret')
      }
         steps {
            bat 'mvn clean deploy -DmuleDeploy -Danypoint.platform.client_id=%CLIENT_ID% -Danypoint.platform.client_secret=%CLIENT_SECRET%'
      }
    }
	     
  }
}
