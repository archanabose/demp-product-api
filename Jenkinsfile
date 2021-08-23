pipeline {

  agent any

  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          echo "****hello no test***"
      }
    }

     stage('Development') {
      environment {
        ENVIRONMENT = 'Sandbox'
        APP_NAME = '<DEV-API-NAME>'
      }
      steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -Pdev -DmuleDeploy '
      }
    }
  }

 
}