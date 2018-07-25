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
        stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'echo \'Run Unit Test\''
          }
        }
        stage('') {
          steps {
            sh 'echo \'Functional Test\''
          }
        }
      }
    }
    stage('package') {
      steps {
        sh 'mvn package'
      }
    }

  }
}
