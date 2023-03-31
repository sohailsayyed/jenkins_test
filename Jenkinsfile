pipeline {
    
    agent any
   
    stages {
      
        stage ('Checkout') {
            when {
                anyOf {
                    expression {  env.GITHUB_REF == "refs/heads/main" } 
                    
                   // expression { env.BRANCH_NAME == "develop" }
                    
                    //expression { env.BRANCH_NAME ==~ "release" }
                    expression {  env.GITHUB_REF == "refs/heads/test" }
                }
            }

            steps {
                checkout scmGit(branches: [[name: '*/main'], [name: '*/develop'], [name: '*/release'], [name: '*/test']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-rootuser', url: 'https://github.com/sohailsayyed/jenkins_test.git']])
                echo "Test stage..! "   
                echo "${env.GITHUB_REF}"
            }
            
        }
        
        stage('Install dependencies') {
            steps {
                
                echo ' stage 1 '
                echo "${env.GITHUB_REF}"
            }
        }
        
        stage('Build') {
            steps {
                echo "2nd stage "
                echo "${env.BRANCH_NAME}"
            }
        }

        
    
    }
}
