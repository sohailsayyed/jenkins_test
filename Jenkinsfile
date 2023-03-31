pipeline {
    
    agent any
   
    stages {
      
        stage ('Checkout') {
            when {
                anyOf {
                    expression { env.BRANCH_NAME == "main" }
                    expression { env.BRANCH_NAME == "develop" }
                    expression { env.BRANCH_NAME ==~ "release" }
                }
            }

            steps {
                checkout scmGit(branches: [[name: '*/main'], [name: '*/develop'], [name: '*/release']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-rootuser', url: 'https://github.com/sohailsayyed/jenkins_test.git']])
                }
        }
        
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                sh 'nohup node server.js &'
            }
        }

        
    
    }
}
