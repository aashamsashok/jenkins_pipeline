pipeline {
  agent any
  stages {
    stage('Check and configure devices') {
      steps {
        sh 'echo "Updating images to required version"'
      }
    }
    stage('functional_tests') {
      parallel {
        stage('onemw-rdk') {
          steps {
            sh '''echo "Wating for free device to execute"&&sleep 10&&echo "Got device. Starting execution"

'''
            sh 'sleep 10'
            sh 'echo "Got device. Starting execution"'
          }
        }
        stage('onemw-pal') {
          steps {
            sh 'echo "Wating for free device to execute"&&sleep 10&&echo "Got device. Starting execution"'
          }
        }
      }
    }
    stage('non-functional-tests') {
      steps {
        sh 'echo "Wating for free device to execute"&&sleep 10&&echo "Got device. Starting execution"'
      }
    }
    stage('Report') {
      steps {
        echo '"Uploading results"'
      }
    }
  }
}
