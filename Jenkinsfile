pipeline {
  agent any
  stages {
    stage('Build For Develop') {
        when { 
          expression {
           git branch: 'origin/develop'
          }
        }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
    stage('Build For Main') {
        when { 
          expression {
           git branch: 'origin/main'
          }
        }
        steps {
             echo "Main branch run successfully..! "
        }
    }
  }
}
