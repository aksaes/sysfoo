pipeline {
  agent any
  
  triggers { pollSCM('H/2 * * * *') }
  tools {
    maven 'Maven 3.6.1'
  }
  stages {
    stage('Build') {
      steps {
        sh 'mavan compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mavan clean test'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package -DskipTests'
      }
    }
  }
}
