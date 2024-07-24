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
                apt-get install python3.11-venv -y
                '''
            }
        }
        stage('Test') {
            steps {
                sh 'apt update'
                sh 'apt upgrade -y'
                sh 'apt-get install python3 -y'
                sh 'apt-get install python3.11-venv -y'
                sh 'python3 -m venv .venv'
                sh '. .venv/bin/activate'
                sh 'pip --version'
                sh 'pip install DateTime'
                sh 'python3 py_text.py'
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