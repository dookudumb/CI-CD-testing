pipeline {
    agent {
        docker {
            image 'node:18' // Use a Docker image based on your tech stack
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Bind Docker for access
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run --rm myapp:latest npm test' // Replace with your test command
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker tag myapp:latest uat-machine:5000/myapp:latest'
                sh 'docker push uat-machine:5000/myapp:latest'
            }
        }
    }
}
