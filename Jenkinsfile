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
                echo "${env.test}"
            }
            
        }
  
    }
}
