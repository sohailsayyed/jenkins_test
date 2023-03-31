pipeline {
    
    agent any
   
    stages {
      
        stage ('Checkout') {
            when {
                
                branch "test"
                
            }
        

            steps {
                
                echo "Test stage..! "   
                echo "${env.GITHUB_REF}"
            }
            
        }
  
    }
}
