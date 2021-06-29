CODE_CHANGES = getGitChanges()
pipeline {
  agent any
  stages{
    when{
      expression {
        BRANCH_NAME == 'main' || CODE_CHANGES == true
      }
    stage("build"){
      steps{
        echo 'building the application'
      }
    }
    stage("test"){
      when{
        expression {
          BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
        }
      }
      steps{
        echo 'testing the application'
      }
    }
    stage("deploy"){
      steps{
        echo 'deploying the application'
      }
    }
  }
}
