pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/my-website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop website || true
                docker rm website || true
                docker run -d --name website -p 80:80 my-website
                '''
            }
        }
    }
}
