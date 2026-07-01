pipeline{
    agent any
    stages{
         stage('Checkout') {
            steps {
                checkout scm
            }
         }
        stage('Build'){
            steps{
                echo 'building the application code'
            }
        }
        stage('Test'){
            steps{
                echo 'testing the application code'
            }
        }
        stage('Deploy'){
            steps{
                echo 'deploying the application code'
            }
        }
    }
}

