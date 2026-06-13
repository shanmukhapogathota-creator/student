pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading Code'
                checkout scm
            }
        }

        stage('Deploy Website') {
            steps {
                bat '''
                if not exist C:\\inetpub\\wwwroot mkdir C:\\inetpub\\wwwroot
                copy /Y student_registration.html C:\\inetpub\\wwwroot\\index.html
                '''
            }
        }

        stage('Verify') {
            steps {
                bat 'curl http://localhost:80'
            }
        }
    }
}
