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
          sh 'docker build -t tontonlaforce/productivity-app:client-latest .'
        }

        dir(path: './mern-app-jenkins/server') {
          sh 'docker build -t tontonlaforce/productivity-app:server-latest .'
        }

      }
    }

    stage('Push Images to DockerHub') {
      steps {
        withCredentials(bindings: [usernamePassword(credentialsId: 'docker_credentials', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
          sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
          sh 'docker push tontonlaforce/productivity-app:client-latest'
          sh 'docker push tontonlaforce/productivity-app:server-latest'
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