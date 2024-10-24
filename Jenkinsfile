pipeline {
    agent any
    tools {
        nodejs 'NodeJS'  // Make sure this matches the name you configured for NodeJS
        maven 'Maven'    // Ensure this matches the name you gave Maven in the Jenkins settings
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Geetamahatme/my-node-app.git', branch: 'main'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Run Selenium Tests') {
            steps {
                sh 'mvn test -Dtest=YourSeleniumTestClass'
            }
        }
    }
    post {
        success {
            echo 'Build and tests were successful!'
        }
        failure {
            echo 'Build or tests failed!'
        }
        always {
            echo 'Cleaning up...'
        }
    }
}
