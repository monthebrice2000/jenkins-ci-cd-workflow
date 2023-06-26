pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        sh 'checkout scm'
      }
    }

    stage('change directory') {
      steps {
        sh 'cd ./mern-app-jenkins'
        sh 'echo "$(pwd)"'
      }
    }

  }
}