pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading Code'
                checkout scm
            }
        }

        stage('Check Files') {
            steps {
                bat 'dir'
            }
        }

        stage('Deploy Website') {
            steps {
                bat '''
                if not exist C:\\inetpub\\wwwroot mkdir C:\\inetpub\\wwwroot
                copy /Y index.html C:\\inetpub\\wwwroot\\index.html
                '''
            }
        }

        stage('Verify Website') {
            steps {
                bat 'curl http://localhost:80'
            }
        }
    }
}
