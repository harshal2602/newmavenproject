pipeline{
    agent any

    stages {
        stage('git scm checkout') {
            steps {
               git 'https://github.com/harshal2602/newmavenproject.git'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
