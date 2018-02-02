pipeline {
  agent any
  stages {
    stage('Check and configure devices') {
      steps {
        sh 'sh "python tdk_driver.py -t get_builds_to_test"'
        script {
          mymethod
        }
        
      }
    }
  }
}