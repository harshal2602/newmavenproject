pipeline {
    agent any

    stages {
        stage('git scm checkout') {
            steps {
                git 'https://github.com/harshal2602/newmavenproject.git'
            }
        }

        stage('validate the code') {
            steps {
                withMaven(jdk: 'JDK_home', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn validate'
                }
            }
        }

        stage('compile the code') {
            steps {
                withMaven(jdk: 'JDK_home', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn compile'
                }
            }
        }

        stage('test the code') {
            steps {
                withMaven(jdk: 'JDK_home', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn test'
                }
            }
        }

        stage('package the code') {
            steps {
                withMaven(jdk: 'JDK_home', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn clean package'
                }
            }
        }
        stage('deploy the code on tomcat') {
            steps {
                sshagent(['DEVCICD']) {
                 sh 'scp -o StrictHostKeyChecking=no  webapp/target/webapp.war ec2-user@34.202.165.116:/usr/share/tomcat/webapps'
                }
            }
        }
    }
}
