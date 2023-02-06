#!/usr/bin/env groovy

String getRepoName () {
  return "$GIT_URL".tokenize('/')[3].split("\\.")[0]
}

String getRepoOwnerName() {
  return "$GIT_URL".tokenize('/')[2].split("\\.")[0]
}


pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        // build steps
        sh 'mvn clean install'
      }
    }
    stage('Test') {
      steps {
        // test steps
        sh 'mvn test'
      }
    }
    stage('Deploy') {
      steps {
        // deploy steps
        sh 'mvn deploy'
      }
    }
  }
}