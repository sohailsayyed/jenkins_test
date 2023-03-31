pipeline {
    
    agent any
   
    stages {
      
        stage ('Checkout') {
            when {
                anyOf {
                    expression { env.BRANCH_NAME == "main" } 
                    
                    expression { env.BRANCH_NAME == "develop" }
                    
                    expression { env.BRANCH_NAME ==~ "release" }
                    expression { env.BRANCH_NAME == "test" }
                }
            }

            steps {
                //checkout scmGit(branches: [[name: '*/main'], [name: '*/develop'], [name: '*/release'], [name: '*/test']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-rootuser', url: 'https://github.com/sohailsayyed/jenkins_test.git']])
                echo "Test stage..! "   
                echo "${env.BRANCH_NAME}"
            }
            
        }
        
        stage('Install dependencies') {
            steps {
                
                echo ' stage 1 '
            }
        }
        
        stage('Build') {
            steps {
                echo "2nd stage "
            }
        }

        
    
    }
}
