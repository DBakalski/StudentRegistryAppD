pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/DBakalski/StudentRegistryAppD'
            }
        }
        stage('Install dependencies') {
            steps {
                script {
                    bat 'npm install'
                }
            }
        }
        stage('Start Application and Run Tests') {
            steps {
                script {
                    bat 'npm start &'               // Starts the application in the background
                    bat 'wait-on http://localhost:8090'  // Waits until the application is accessible
                    bat 'npm test'                 // Runs the tests
                }
            }
        }
    }
    
    post {
        always {
            echo "CI pipeline completed"
        }
    }
}