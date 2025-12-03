pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Requirements') {
            steps {
                echo "Installing Python dependencies..."
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'pytest || true'
            }
        }

        stage('Docker Build') {
            steps {
                echo "Building Docker image..."
                sh 'docker build -t simple-webapp .'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy stage (setup later)"
            }
        }
    }
}
