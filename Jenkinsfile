pipeline {
    agent any
    

    environment {
        DOCKERHUB_REPO = "chebishev/jenkins-test"
        IMAGE = DOCKERHUB_REPO + ":1.0.$BUILD_NUMBER"
    }
    stages {
        stage('Build') {
            steps {
                echo env.IMAGE
            }
        }
    }
}