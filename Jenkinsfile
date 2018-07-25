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
            sh 'echo \'functional test\''
          }
        }
      }
    }
    stage('package') {
      steps {
        sh 'mvn package'
      }
    }
    stage('Archive Artifacts') {
      steps {
        archiveArtifacts 'target/demowebapp.war'
      }
    }
  }
}