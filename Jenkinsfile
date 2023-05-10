pipeline {

  agent any
         
  stages {
    stage('Test') {
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
            bat 'clean deploy -DmuleDeploy -Danypoint.platform.client_id=%CLIENT_ID% -Danypoint.platform.client_secret=%CLIENT_SECRET%'
      }
    }
	     
  }
}
