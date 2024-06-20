pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git 'https://github.com/KaushalyaN/jenkins-My_NodeJs_Application.git'
            }
        }

        stage('Build') {
            steps {
                // Install dependencies
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Run tests
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application
                // Start the Node.js server
                sh 'nohup npm start &'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
            // You can add additional actions on success, such as notifications
        }
        failure {
            echo 'Deployment failed!'
            // You can add actions to take on failure, such as sending notifications or rolling back changes
        }
    }
}

