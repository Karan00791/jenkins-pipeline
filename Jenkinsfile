pipeline{
    agent any
   tools{
    maven'Maven'
   }
   environment
{
    APP_NAME = 'hello-world-war'
    DEPLOY_DIR ='/var/lib/tomcat10/webapps'
}

    stages{
         stage('Checkout') {
            steps {
                echo 'dowloading source code from GIT HUB'
                checkout scm
                sh 'pwd'
                sh 'ls -la'
            }
         }
         stage ('verify environment'){
            steps{
                sh 'java -version'
                sh 'maven -version'
                sh 'git -version'

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
                echo "testing the application code with"
            }
        }
        stage('Deploy'){
            steps{
                echo 'deploying the application code'
                sh "sudo cp target/*.war ${DEPLOY_DIR}/ "
                
            }
        }
    }
}

