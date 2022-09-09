pipeline {
  agent any
  stages {
    stage('Deploy CloudHub') {
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        withMaven(maven: 'Default') {
          sh "echo JAVA_HOME=$JAVA_HOME"
          sh "mvn clean"
          sh 'mvn clean package deploy -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW} -DmuleDeploy' 
        }
      }
    }
  }
}
