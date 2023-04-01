pipeline {
  agent any
  stages {
    stage('Build For Develop') {
        when { 
          expression {
           git branch: 'develop'
          }
        }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
    stage('Build For Main') {
        when { 
          expression {
           git branch: 'main'
          }
        }
        steps {
             echo "Main branch run successfully..! "
        }
    }
  }
}
