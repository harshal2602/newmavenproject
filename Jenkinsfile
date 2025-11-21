pipeline{
    agent any

    stages {
        stage('git scm checkout') {
            steps {
               git 'https://github.com/harshal2602/newmavenproject.git'
            }
        }
        stage('validate the code') {
            steps {
                withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn validate'
                }
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
stage('compile the code') {
            steps {
                withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn compile'
                }
                
            }
        }
