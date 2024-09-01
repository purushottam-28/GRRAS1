pipeline {
	agent{
		label 'slave-label'
	}

	stages {
		stage('Checkout') {
			steps {
				checkout scm
			}
		}
		stage('Build') {
			steps {
				sh 'mvn install'
			}
		}
		stage('Deployment') {
			steps {
				sh 'cp target/Project1.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
			}
		}
	}
}
