#!/usr/bin/env groovy

String getRepoName () {
  return "$GIT_URL".tokenize('/')[3].split("\\.")[0]
}

String getRepoOwnerName() {
  return "$GIT_URL".tokenize('/')[2].split("\\.")[0]
}


pipeline {
    agent any
	parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'main', name: 'BRANCH', type: 'PT_BRANCH'
    }

    stages {
        stage('Build') {
          steps {
         /**  glMavenBuild javaVersion:"11.0", 
			    mavenGoals: "-f pom.xml clean install"  **/
				
		/**glMavenBuild pomFile: 'pom.xml',
                runJacocoCoverage: false,
                uploadJacocoResults: false   **/
			
			
		/**git url: 'https://github.com/sumanmanjhi28/calculator.git'    **/
        git branch: "${params.BRANCH}", url: 'https://github.com/sumanmanjhi28/calculator.git' 
/** withMaven {
      sh "mvn clean "            **/
	  
	  sh 'mvn -B -DskipTests clean package'
		
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