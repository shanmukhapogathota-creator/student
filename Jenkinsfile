pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading Code'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t student-registration .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f student-container || exit 0'
                bat 'docker run -d --name student-container -p 80:80 student-registration'
            }
        }
    }
}
