pipeline {
  agent any
  tools { 
        maven 'maven' 
        
    }
  stages {
    stage('code pull') {
      steps {
        checkout scm
        echo 'Git checkout complete'
      }
    }
    stage('build') {
      steps {
         sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
      }
    }
    stage('test') {
      steps {
        parallel(
          "code analyze": {
            echo 'd'
            
          },
          "unit tests": {
            echo 'a'
            
          }
        )
      }
    }
    stage('package') {
      steps {
        echo 'e'
      }
    }
    stage('regression test') {
      steps {
        echo 'f'
      }
    }
    stage('qa-deploy') {
      steps {
        echo 'yo'
      }
    }
  }
}