pipeline {
  agent any
  stages {

    stage('Build') {
         steps {
            script {
                def commit = checkout scm
                // we set BRANCH_NAME to make when { branch } syntax work without multibranch job
                env.BRANCH_NAME = commit.GIT_BRANCH.replace('origin/', '')
                echo "${env.BRANCH_NAME}"
                

                //actually build ...
                }
            }
        }

    stage('Build For Develop') {
        when { 
          expression { env.BRANCH_NAME == "develop" }
        }
        steps {
             echo "Develop branch run successfully..! "
        }
    }
    stage('Build For Main') {
        when { 
          expression { env.BRANCH_NAME == "main"}
        }
        steps {
             echo "Main branch run successfully..! "
        }
    }
  }
}
