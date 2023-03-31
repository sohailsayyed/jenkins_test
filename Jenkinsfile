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
        
        stage('My Conditional Stage') {
            when (BRANCH_NAME == 'test') {
                echo 'Only on master branch.'
                }
                steps {
                    echo "Test stage run successfully..! "
                }      
            }
        
        stage ('Checkout') {
            when {
                expression {
                    return env.BRANCH_NAME == 'test'
                }
                
            }
        

            steps {
                
                echo "Test stage run successfully..! "   
                echo "${env.BRANCH_NAME}"
            }
            
        }
  
    }
}
