pipeline {
	agent any

	stages {
	    stage('Checkout') {
	        steps {
				checkout scm
			}
		}
		stage('Build') {
	        steps {
				sh '/home/adil/Software/apache-maven-3.6.0/bin/mvn install'
	        }
		}
		stage('Deployment') {
			steps {
				sh 'sshpass -p "1234" scp target/gamutkart.war asif@172.17.0.2:/home/adil'
				sh 'sshpass -p "1234" scp target/gamutkart.war adil@172.17.0.3:/home/web'
				
			}
		}

	}
}
