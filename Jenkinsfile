pipeline {
  agent {
    node {
      label 'tdk_executor'
    }
    
  }
  stages {
    stage('Check and configure devices') {
      steps {
        sh 'sh "python tdk_driver.py -t get_builds_to_test"'
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