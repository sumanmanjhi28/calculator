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
			    git url: 'https://github.com/sumanmanjhi28/calculator.git'
                withMaven {
				sh "mvn clean"
				}
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}