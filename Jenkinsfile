pipeline {
    agent any
    stages {
        stage('git SCM Checkout') {
            steps {
                git 'https://github.com/harshal2602/newmavenproject.git'
            }
        }
        stage('compile The Code') {
            steps {
                withMaven(jdk: 'JDK_home', maven: 'Maven_home', traceability: true) {
                    sh 'mvn Compile'
                }
            }
        }
    }
}
