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
                sh "sudo cp /home/ubuntu/.m2/repository/com/efsavage/hello-world-war/1.0.0/hello-world-war-1.0.0.war /var/lib/tomcat10/webapps "
                
            }
        }
    }
}

