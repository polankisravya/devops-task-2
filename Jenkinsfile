pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image for Polanki...'
                sh 'docker build -t polanki-nginx-site .'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Running container for Task 2...'
                // Stop and remove old container if it exists
                sh 'docker rm -f polanki-nginx-container || true'
                // Run on port 8081
                sh 'docker run -d -p 8081:80 --name polanki-nginx-container polanki-nginx-site'
            }
        }
    }
}
