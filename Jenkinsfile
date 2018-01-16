pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        checkout scm
      }
    }

    stage('compile') {
      steps {
        sh './gradlew clean compileJava'
      }
    }

    stage('test') {
      steps {
        sh './gradlew test'
      }
    }
  }
}
