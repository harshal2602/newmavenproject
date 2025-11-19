pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                git 'https://github.com/harshal2602/newmavenproject.git'
            }
        }
        stage('level-1') {
            steps {
                sh 'echo Pune'
            }
        }
        stage('level-2') {
            steps {
                sh 'echo New York'
            }
        }
    }
}
