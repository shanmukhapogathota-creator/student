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

        stage('Deploy Student Website') {
            steps {
                bat '''
                if not exist C:\\inetpub\\wwwroot\\student mkdir C:\\inetpub\\wwwroot\\student

                copy /Y index.html C:\\inetpub\\wwwroot\\student\\index.html
                '''
            }
        }

        stage('Verify Website') {
            steps {
                bat 'curl http://localhost/student'
            }
        }
    }
}
