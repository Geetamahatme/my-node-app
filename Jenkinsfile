pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                // Add your build commands here, if any
                sh 'npm run build' // Adjust this command based on your project structure
            }
        }
        stage('Run Application') {
            steps {
                // Command to run your application
                sh 'npm start' // or whatever command you use to run your app
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
