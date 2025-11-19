pipeline {
    agent any
    stages {
        stage('git SCM Checkout') {
            steps {
                git 'https://github.com/harshal2602/newmavenproject.git'
            }
        }
        stage('package The Code') {
            steps {
                withMaven(jdk: 'JDK_home', maven: 'Maven_home', traceability: true) {
                    sh 'mvn clean package'
                }
            }
        }
        stage('deploy the code on tomcat server') {
            steps {
                sshagent(['DEVCICD']) {
                 sh 'scp -o StrictHostKeyChecking=no  webapp/target/webapp.war ec2-user@172.31.27.172:usr/share/tomcat/webapps
                }
            }
        }
    }
}
