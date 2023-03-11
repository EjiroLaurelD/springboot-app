pipeline {
  tools {
    maven 'maven3'  
  }
  agent any
  environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhub')
  }
  stages {
    stage ('Buid image') {
        steps {
            sh 'docker build -t ejirolaureld/pipeline .'
        }
    }
    stage ('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage ('Push') {
      steps {
        sh 'docker push ejirolaureld/pipeline'
      }
    }
  }
}


   
