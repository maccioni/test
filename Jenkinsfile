pipeline {
    agent any

    stages {
        stage('Stage 1') {
            steps {
              echo "Check enviroment "
              sh "env"
              echo "Get input"
              input message: 'Continue to the next stage?'
            }
        }
        stage('Stage 2') {
            steps {
              echo "Running Stage 2"
            }
        }
        stage('Stage 3') {
            steps {
              echo "Running Stage 3"
            }
        }
    }
}
