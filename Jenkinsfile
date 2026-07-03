pipeline{
    agent any
    environment{
        FINAL_VERSION ='1.0'
        SERVER_CREDS =credentials('demo-server-cred')
    }
    stages{
         stage('Checkout') {
            steps {
                checkout scm
            }
         }
        stage('Build'){
            steps{
                echo 'building the application code webhoooooooooks'
            }
        }
        stage('Test'){
            steps{
                echo "testing the application code with ${FINAL_VERSION}"
            }
        }
        stage('Deploy'){
            steps{
                echo 'deploying the application code'
                echo "deploying the code with ${SERVER_CREDS}"
            }
        }
    }
}

