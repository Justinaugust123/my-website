pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
}
