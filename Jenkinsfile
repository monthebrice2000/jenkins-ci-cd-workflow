pipeline {
  agent any
  stages {
    stage('change directory') {
      steps {
        sh 'cd ./mern-app-jenkins'
        dir(path: './mern-app-jenkins') {
          sh 'echo "$(pwd)"'
        }

      }
    }

  }
}