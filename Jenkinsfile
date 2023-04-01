pipeline {
  agent any
  stages {
    stage('Build For Develop') {
        when { 
          expression {
            branch 'develop'
          }
        }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
    stage('Build For Main') {
        when { 
          expression {
            branch 'main'
          }
        }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
  }
}
