pipeline{
    agent any
   tools{
    maven'Maven'
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
                sh "mvn install"
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
                
            }
        }
    }
}

