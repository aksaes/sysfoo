pipeline {
  agent any
  
  triggers { pollSCM('H/2 * * * *') }
  tools {
    maven 'Maven 3.6.3'
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn clean test'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package -DskipTests'
      }
    }
  }
}
