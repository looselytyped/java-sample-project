pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '50'))
    timeout(time: 1, unit: 'HOURS')
    timestamps()
  }
  tools {
    jdk 'JDK 8u162'
  }

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
