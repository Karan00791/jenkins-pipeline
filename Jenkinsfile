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
                echo 'dowloading source code from GIT HUB repo'
                checkout scm
                sh 'pwd'
                sh 'ls -la'
            }
         }
         stage ('verify environment'){
            steps{
                sh 'java -version'
                sh 'mvn -version'
                sh 'git --version'

            }
         }
        stage('compile'){
            steps{
                echo 'compiling the application code'
                sh "mvn clean compile"
            }
        }
        stage('Unit Test'){
            steps{
                echo "testing the application code with"
                sh "mvn test"
            }
        }
            stage('pacaakage'){
                steps{
                    echo'creating the war file'
                    sh 'mvn package'
                }
            }

        }
        stage('Deploy to Tomcat'){
            steps{
                echo 'deploying the application code'
                sh "sudo cp target/*.war ${DEPLOY_DIR}/ "
                
            }
        }
    }
    post{

     always{
    echo 'pipeline finished'
    }

    success{
echo 'application was successfully build and deployed'
    }

    failure{
        echo'build failed'
    }

    }
