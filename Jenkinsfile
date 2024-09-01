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
				sh 'JAVA_HOME=/home/grras/slavedir/jdk-11.0.24 /home/grras/slavedir/apache-maven-3.9.9/bin/mvn install'
			}
		}
		stage('Deployment') {
			steps {
				sh 'cp target/GRRAS1.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
			}
		}
		stage('slack notification') {
			steps {
				slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '# devops-notification', color: 'good', message: 'Welcome to Jenkins slack world', teamDomain: 'GRRAS', tokenCredentialId: 'slacknotifier'
			}
		}
	}
}
