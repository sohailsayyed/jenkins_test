pipeline {
    environment {
        ENVIRONMENT = 'test'
    }
    
    agent any
   
    stages {
        
        stage('Start') {
            steps {
                echo "Test stage run successfully..! "
            }
        }

        
        stage ('Checkout') {
            when {
                expression {
                     branch 'test'
                }
                
            }
        

            steps {
                
                echo "Test stage run successfully..! "   
                echo "${env.test}"
            }
            
        }
  
    }
}
