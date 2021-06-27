pipeline {

  agent none

  environment {
    DOCKER_IMAGE = "mjzzyou137/cicd"
  }

  stages {
    stage("Test") {
      agent {
          docker {
            image 'mhart/alpine-node:slim-12'
            args '-u 0:0 -v /tmp:/root/.cache'
          }
      }
      steps {
        sh "npm install"
        sh "npm run test"
      }
    }
  }

  post {
    success {
      echo "SUCCESSFUL"
    }
    failure {
      echo "FAILED"
    }
  }
}
