pipeline {
    agent {
        label 'slave1'
    }
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
        stage('tomcat installation') {
            steps {
                sh 'sh tomcat.sh'
                echo "tomcat installed"
            }
        }
        stage('deploy') {
            steps {
                echo "good"
                sh 'sudo cp /home/ubuntu/workspace/tomcatAssignment/target/hello-world-war-3.0.0.war /var/lib/tomcat9/webapps'
            }
        }
    }
}
