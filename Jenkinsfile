pipeline {
    agent any
    triggers {
        pollSCM '*/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                apt update
                apt upgrade -y
                apt-get install python3 -y
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                python3 -V
                '''
            }
        }
        stage('Deliver') {
            steps {
                sh '''
                echo "Ready to deliver"
                '''
            }
        }
    }
}