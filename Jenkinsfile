pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Files') {
            steps {
                sh 'ls -la'
                sh 'test -f index.html'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t advanced-weather-app:1.0 .'
            }
        }

        stage('Docker Deploy') {
            steps {
                sh '''
                    docker rm -f advanced-weather-app || true
                    docker run -d --name advanced-weather-app -p 8081:80 advanced-weather-app:1.0
                '''
            }
        }
    }
}
