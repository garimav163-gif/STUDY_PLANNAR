pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }
        stage('Verify Files') {
            steps {
                bat 'if exist index.html (echo index.html found) else (echo MISSING index.html && exit 1)'
                bat 'if exist landing.html (echo landing.html found) else (echo MISSING landing.html && exit 1)'
                bat 'if exist signup.html (echo signup.html found) else (echo MISSING signup.html && exit 1)'
            }
        }
        stage('Build') {
            steps {
                echo 'Static site verified — ready to deploy'
            }
        }
    }
    post {
        success {
            echo 'SUCCESS: all files present and verified.'
        }
        failure {
            echo 'FAILURE: something is missing. Check the failed stage.'
        }
    }
}