pipeline {
    agent any
    environment {
        DOCKERHUB_REPO = "chebishev/jenkins-test"
    }
    
    stages {
        stage("Setup"){
            steps{
                script {
                    def full_repo = "${env.DOCKERHUB_REPO}:1.0.${BUILD_NUMBER}"
                    echo "Full repo: ${full_repo}"
                }
            }
        }
        stage('Build') {
            steps {
                echo "TEST 1: Variable in the same stage"
                script {
                    echo "Full repo: ${env.DOCKERHUB_REPO}:1.0.${BUILD_NUMBER}"
                }
                echo "End test 1"
            }
        }
        stage('Test') {
            steps {
                echo "TEST 2: Variable from different stage"
                script {
                    echo "Full repo: ${env.DOCKERHUB_REPO}:1.0.${BUILD_NUMBER}"
                }
                echo "End test 2"
            }
        }
        stage("Deploy") {
            steps{
                echo "TEST 3: Variable from different stage, not concatenated with other strings"
                script {
                    def full_repo = "${env.DOCKERHUB_REPO}:1.0.${BUILD_NUMBER}"
                    echo "Full repo: ${full_repo}"
                }
                echo "End test 3"
            }
        }
    }
}
