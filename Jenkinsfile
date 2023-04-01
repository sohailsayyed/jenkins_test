pipeline {
  agent any
  stages {
    stage('Build For Develop') {
        when { branch 'develop' }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
    stage('Build For Main') {
        when { branch 'main' }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
  }
}
