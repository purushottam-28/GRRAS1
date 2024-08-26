pipeline {
	agent any

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
				sh 'cp target/GRRAS1.war /home/purushottam/Documents/DevOps/apache-tomcat-9.0.93/webapps'
				}}
		}
