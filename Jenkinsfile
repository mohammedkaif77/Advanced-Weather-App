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

        stage('Build') {
            steps {
                echo 'Static website build completed'
            }
        }
    }
}
