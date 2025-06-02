pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run --rm myapp:latest npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker push myapp:latest'
            }
        }
    }
}
