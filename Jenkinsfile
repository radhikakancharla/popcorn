pipeline {
  agent any
  stages {
    stage('greetings') {
      steps {
        sh 'echo "hello world"'
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
        sh '''docker login -u radhikakancharla -p ____
docker push radhikakancharla/popcorn:$BUILD_NUMBER'''
      }
    }
  }
}