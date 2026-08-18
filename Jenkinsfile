pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                bat 'echo Building application on Windows...'
                bat 'if not exist build mkdir build'
                bat 'copy /Y index.html build\\index.html'
            }
        }

        stage('Test') {
            steps {
                bat 'if exist build\\index.html (echo TEST PASSED) else (echo TEST FAILED & exit /b 1)'
            }
        }

        stage('Deploy') {
            steps {
                bat 'if not exist deployment mkdir deployment'
                bat 'copy /Y build\\index.html deployment\\index.html'
                echo 'Application deployed successfully.'
            }
        }
    }
}