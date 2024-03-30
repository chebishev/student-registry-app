pipeline {
    agent any
    environment {
        DOCKERHUB_REPO = "chebishev/jenkins-test"
    }
    
    stages {
        stage('Build') {
            steps {
                full_repo = env.DOCKERHUB_REPO + ":1.0.$BUILD_NUMBER"
                echo "Full repo first occurence: $full_repo"
            }
        }
        stage('Test') {
            steps {
                echo "Full repo second occurence: $full_repo"
            }
        }
        stage("Deploy") {
            echo $full_repo
    }
}