pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading Code'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f student-container || true'
                sh 'docker run -d -p 8081:80 --name student-container student-app'
            }
        }
    }
}
