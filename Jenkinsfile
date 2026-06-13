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
                del /Q C:\\inetpub\\wwwroot\\*
                copy /Y index.html C:\\inetpub\\wwwroot\\index.html
                '''
            }
        }

        stage('Verify') {
            steps {
                bat 'curl http://localhost'
            }
        }
    }
}
