pipeline {
    agent any
    environment {
        DOCKERHUB_REPO = "chebishev/jenkins-test"
    }
    
    stages {
        stage("Setup"){
            steps{
                full_repo = env.DOCKERHUB_REPO + ":1.0.$BUILD_NUMBER"
            }
        }
        stage('Build') {
            steps {
                echo "TEST 1: Variable in the same stage"
                echo "Full repo first occurence: $full_repo"
                echo "End test 1"
            }
        }
        stage('Test') {
            steps {
                echo "TEST 2: Variable from different stage"
                echo "Full repo second occurence: $full_repo"
                echo "End test 2"
            }
        }
        stage("Deploy") {
            steps{
                echo "TEST 3: Variable from different stange, not concatenated with other strings"
                echo $full_repo
                echo "End test 3"
                }
            
        }
    }
}