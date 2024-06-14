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
			
		stage ('Deploy to tomcat server') {
           steps {
             script {
              deploy adapters: [tomcat9(credentialsId: 'tomcat-creds', path: '', url: 'http://10.0.0.239:9090')], contextPath: '/webapp01', onFailure: false, war: 'target/*.war' 
        }
      }
    }
			
	
   }
}

