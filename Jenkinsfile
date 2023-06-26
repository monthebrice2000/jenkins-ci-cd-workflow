pipeline {
  agent any
  environment {
	  MONGODB_URI = credentials('mongodb_uri')
	  TOKEN_KEY = credentials('token_key')
	  EMAIL = credentials('email')
	  PASSWORD = credentials('password')
  }
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
