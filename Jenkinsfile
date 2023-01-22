pipeline {

  agent any

  options {

    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')

  }

  stages {

    stage('Prepare') {

      steps {

        sh '''

          java -version

        '''

      }

    }
    stage('Build') {

      steps {

        echo "Building........."
      }

    }
    
    
   
    
    stage('Deliver') {

      steps {

        echo "Pushing....."

      }

    }

  }
  
}
