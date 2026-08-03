pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh '''
                if command -v docker-compose >/dev/null 2>&1; then
                    docker-compose build
                else
                    docker compose build
                fi
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                if command -v docker-compose >/dev/null 2>&1; then
                    docker-compose up -d
                else
                    docker compose up -d
                fi
                '''
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
