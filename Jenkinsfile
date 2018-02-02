pipeline {
  agent {
    node {
      label 'tdk_executor'
    }
    
  }
  stages {
    stage('Check and configure devices') {
      steps {
        sh 'sh "echo "Updating images to required version"'
      }
    }
    stage('functional_tests') {
      parallel {
        stage('onemw-rdk') {
          steps {
            sh '''echo "Wating for free device to execute"
sleep 10
echo "Got device. Starting execution"
'''
          }
        }
        stage('onemw-pal') {
          steps {
            sh '''echo "Wating for free device to execute"
sleep 10
echo "Got device. Starting execution"'''
          }
        }
      }
    }
    stage('non-functional-tests') {
      steps {
        sh '''echo "Wating for free device to execute"
sleep 10
echo "Got device. Starting execution"'''
      }
    }
    stage('Report') {
      steps {
        echo '"Uploading results"'
      }
    }
  }
}