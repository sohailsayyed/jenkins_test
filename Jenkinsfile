Final Working RI Frontend Pipeline

-------------------------------------------------------------------------------------------------------------


pipeline {
    environment {
        ENVIRONMENT = 'test'
    }
    
    agent any
   
    stages {
        
        stage('Start') {
            steps {
                echo "Start stage run successfully..! "
            }
        }

        
        stage ('Checkout') {
            
            when {
                anyOf{
                    expression {
                         
                         branch 'main'
                         branch 'develop'
                         branch 'release'
                    }
                }
            }
        

            steps {
                
                echo "Test stage run successfully..! " 
                checkout scmGit(branches: [[name: '*/main'], [name: '*/develop'], [name: '*/release']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-rootuser', url: 'https://github.com/sohailsayyed/jenkins_test.git']])

                echo "${env.branch}"

                sh 'npm install'
                sh 'nohup node server.js &'
            }
            
        }

        stage('Final Steps') {

             when {
                anyOf{
                    expression {
                         
                        branch 'main'
                        branch 'release'
                    }
                }
            }

            steps {

                //sh 'aws s3 sync build s3://ri-frontend/'

                sh 'scp -r *  ubuntu@13.233.236.84:/home/ubuntu/jenkins_test/'
                sh 'node app.js'
                
                echo "+++Upload Successful+++"
            }
        }
  
    }
}
