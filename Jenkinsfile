pipeline {
    agent none
      stages {
        stage('checkout') {
	    agent {
	     label 'slave1'
            }
            steps {
		sh 'rm -rf hello-world-war'    
		sh 'git clone https://github.com/chetanJain19/hello-world-war.git'
            }
        }
	stage('Build') {
	    agent {
	    label 'slave1'
            }
            steps {		
		sh 'mvn clean package'
	    }
	}
        stage('deploy') {
	     agent {
	     label 'slave2'
            }
            steps {
		    echo "good "
	            // sh 'sudo cp /var/lib/jenkins/workspace/multiBranchPipeLineOne/target/hello-world-war-3.0.0.war /var/lib/tomcat9/webapps'//
            }
        }    
    }
}
