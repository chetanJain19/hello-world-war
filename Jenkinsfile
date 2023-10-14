pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {	
		sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/chetanJain19/hello-world-war/'
            }
        }
	stage('Build') {
            steps {					
                sh 'mvn clean package'
            }
        }
	stage('deploy') {
            steps {
                sh 'sudo cp /var/lib/jenkins/workspace/multiBranchPipeLineOne_developer/target/hello-world-war-1.0.0.war /var/lib/tomcat9/webapps'
            }
        }	    
    }
}
