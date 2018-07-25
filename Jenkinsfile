pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/pmisarwala/demowebapp.git'
      }
    }
    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }
    stage('package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}