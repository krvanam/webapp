pipeline {

    agent {label 'maven_build_server'}
	
	tools {
        maven 'maven' 
    }
	
    stages {
        stage('Maven Build stage') {
            steps {
                sh 'mvn clean install'
            }

	
        }
    }
}
