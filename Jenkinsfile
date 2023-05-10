pipeline {

  agent any
         
  stages {
    stage('Test') {
      steps {
          echo  'hello world Munit test case'
      }
    }

     stage('Development')      {
         
         environment {
        CLIENT_ID = credentials('connectedAppClientId')
        CLIENT_SECRET = credentials('connectedAppClientSecret')
      }
         steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -PDevelopment -DmuleDeploy -Danypoint.platform.client_id=%CLIENT_ID% -Danypoint.platform.client_secret=%CLIENT_SECRET%'
      }
    }
	     
  }
}