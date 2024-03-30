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
                    // Store the value in an environment variable for access in subsequent stages
                    env.FULL_REPO = full_repo
                }
            }
        }
        stage('Build') {
            steps {
                echo "TEST 1: Variable in the same stage"
                echo "Call from Build stage: ${env.FULL_REPO}"
                echo "End test 1"
            }
        }
        stage('Test') {
            steps {
                echo "TEST 2: Variable from different stage"
                echo "Call from Test stage: ${env.FULL_REPO}"
                echo "End test 2"
            }
        }
        stage("Deploy") {
            steps{
                echo "TEST 3: Variable from different stage, not concatenated with other strings"
                echo ${env.FULL_REPO}
                echo "End test 3"
            }
        }
    }
}
