pipeline {
    agent anyz
    
    stages {
        stage('Build') {
            steps {
                bat "npm install"
            }
        }
        stage('Test') {
            steps {
                bat "npm run test"
            }
        }
    }
}