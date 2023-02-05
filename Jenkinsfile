pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
			    git url: 'https://github.com/sumanmanjhi28/calculator.git'
                withMaven {
				sh "mvn clean verify"
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