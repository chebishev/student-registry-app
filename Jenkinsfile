pipeline {
    agent any
    

    environment {
        DOCKERHUB_REPO = "chebishev/jenkins-test"
    }
    stages {
        stage('Build') {
            steps {
                echo env.DOCKERHUB_REPO + ":1.0.$BUILD_NUMBER"
            }
        }
    }
}