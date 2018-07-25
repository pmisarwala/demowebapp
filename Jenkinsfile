pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/pmisarwala/demowebapp.git', branch: 'feature1')
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
        stage('error') {
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