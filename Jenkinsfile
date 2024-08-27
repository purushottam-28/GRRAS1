pipeline {
	agent any
	parameters {
  		choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIRONMENT'
	}

	stages {
		stage('Checkout') {
			steps {
				checkout scm
				}}
		stage('Build') {
			steps {
				sh '/home/purushottam/Documents/DevOps/apache-maven-3.9.8/bin/mvn install'
				}}
		stage('Deployment') {
			steps {
				script {
				if ( "${env.ENVIRONMENT}" == "QA" ){
					sh 'cp target/GRRAS1.war /home/purushottam/Documents/DevOps/apache-tomcat-9.0.93/webapps'
					echo "deployment has been done on QA!"
				}
				else if  ( "${env.ENVIRONMENT}"== "UAT" ){
         				sh 'cp target/GRRAS1.war /home/purushottam/Documents/DevOps/apache-tomcat-9.0.93/webapps'
					echo "deployment has been done on UAT!"
				}
				echo "deployment has been done!"
				
				}}}
		}
	}
