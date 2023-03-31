pipeline {
    environment {
        ENVIRONMENT = 'test'
    }
    
    agent any
   
    stages {
      
        stage ('Checkout') {
            when {
                expression {
                    return env.BRANCH_NAME == 'test'
                }
                
            }
        

            steps {
                
                echo "Test stage run successfully..! "   
                echo "${env.ENVIRONMENT}"
            }
            
        }
  
    }
}
