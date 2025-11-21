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
                withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn validate'
                }
            }
        }
        stage('compile the code') {
            steps {
                withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
                    sh 'mvn compile'
                }
                stage('test the code') {
                    steps {
                        withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
                            sh 'mvn test'
                        }
                        stage('create the packagee') {
                            steps {
                                withMaven(jdk: 'JAVA_HOME', maven: 'MVN_HOME', traceability: true) {
                                    sh 'mvn package'
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
