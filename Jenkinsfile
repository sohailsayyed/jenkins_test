pipeline {
    environment {
        ENVIRONMENT = 'test'
    }
    
    agent any
   
    stages {
      
        stage ('Checkout') {
            when {
                
                branch "test"
                
            }
        

            steps {
                
                echo "Test stage run successfully..! "   
                echo "${env.ENVIRONMENT}"
            }
            
        }
  
    }
}
