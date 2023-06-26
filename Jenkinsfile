pipeline {
  agent any
  stages {
    stage('Client tests') {
      steps {
        dir(path: './mern-app-jenkins/client') {
          sh 'echo "$(pwd)"'
          sh 'npm install'
          sh 'npm run test'
        }

      }
    }

  }
}