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

    stage('Server tests') {
      steps {
        dir(path: './mern-app-jenkins/server') {
          sh '''npm install
'''
          sh 'export MONGODB_URI=$MONGODB_URI'
          sh '''export TOKEN_KEY=$TOKEN_KEY
'''
          sh 'export EMAIL=$EMAIL'
          sh 'export PASSWORD=$PASSWORD'
          sh 'npm run test'
        }

      }
    }

    stage('Build Image') {
      steps {
        dir(path: './mern-app-jenkins/client') {
          sh 'sudo docker build -t tontonlaforce/productivity-app:client-latest client'
        }

        dir(path: './mern-app-jenkins/server') {
          sh 'sudo docker build -t tontonlaforce/productivity-app:server-latest server'
        }

      }
    }

  }
  environment {
    MONGODB_URI = credentials('mongodb_uri')
    TOKEN_KEY = credentials('token_key')
    EMAIL = credentials('email')
    PASSWORD = credentials('password')
  }
}