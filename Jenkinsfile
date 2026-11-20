pipeline {
  agent any
  stages{
    stage('Chechout'){
    steps{
      checkout scm
    }
  }
  stage(build){
    steps {
      echo 'Checking python application'
      bat'python -m py_compile app.py'
    }
  }
  stage('test'){
    steps{
      echo'Executing automated tests'
      bat'python -m unittest app'
    }
  }
    stage('run application'){
      steps{
        bat'python app.py'
      }
    }
  }
  post{
    Success{
      echo'CI Pipeline completed successfully'
    }
    failure{
      echo'CI pipiline failed'}
  }
}
      
