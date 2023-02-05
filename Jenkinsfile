#!/usr/bin/env groovy

String getRepoName () {
  return "$GIT_URL".tokenize('/')[3].split("\\.")[0]
}

String getRepoOwnerName() {
  return "$GIT_URL".tokenize('/')[2].split("\\.")[0]
}


pipeline {

    agent any
    tools {
        maven 'Maven_3.5.2' 
    }
    stages {
        stage('Compile stage') {
            steps {
                bat "mvn clean compile" 
        }
    }

         stage('testing stage') {
             steps {
                bat "mvn test"
        }
    }

          stage('deployment stage') {
              steps {
                bat "mvn deploy"
        }
    }

  }

}