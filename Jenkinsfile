pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/chetanJain19/hello-world-war.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                sh 'sudo cp $WORKSPACE/target/hello-world-war-3.0.0.war /var/lib/tomcat9/webapps'
            }
        }
    }
}
