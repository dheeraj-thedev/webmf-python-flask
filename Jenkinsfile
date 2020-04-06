pipeline {
  agent {
    docker {
      label "docker && linux" 
      image "python:3.7"
      pwd "."
    }
 }
  
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
