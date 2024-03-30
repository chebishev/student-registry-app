pipeline {
    agent any
    environment {
        DOCKERHUB_REPO = "chebishev/jenkins-test"
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    def full_repo = "${env.DOCKERHUB_REPO}:1.0.${BUILD_NUMBER}"
                    echo "Full repo: ${full_repo}"
                }
                echo "TEST 1: Variable in the same stage"
                echo "Called From Build stage: ${full_repo}"
                echo "End test 1"
            }
        }
        stage('Test') {
            steps {
                echo "TEST 2: Variable from different stage"
                echo "Called From Test stage " + ${full_repo}
                echo "End test 2"
            }
        }
        stage("Deploy") {
            steps{
                echo "TEST 3: Variable from different stage, not concatenated with other strings"
                echo "${full_repo}"
                echo "End test 3"
            }
        }
    }
}
