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
                         branch 'test'
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
            steps {
                echo "Final stage run successfully..! "
            }
        }
  
    }
}
