pipeline {
  agent any
  environment {
   DOCKER_PASSWORD = credentials('DOCKER_PASSWORD')
 }
  stages {
    stage('greetings') {
      steps {
        sh 'echo "hello world"'
      }
    }
     stage('testing') {
      steps {
        rails test
      }
    }
    stage('build docker') {
      steps {
        sh '''docker build -t radhikakancharla/popcorn:$BUILD_NUMBER .

'''
      }
    }
    stage('docker push') {
      steps {
        sh '''docker login -u radhikakancharla -p $DOCKER_PASSWORD
docker push radhikakancharla/popcorn:$BUILD_NUMBER'''
      }
    }
  }
}