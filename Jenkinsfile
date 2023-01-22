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
    
    stage ("Prompt for input") {
      steps {
        script {
          env.USERNAME = input message: 'Please enter the username',
                             parameters: [choice(
                                choices: ['ONE', 'TWO'], 
                                name: 'PARAMETER_01'
                            )]
          env.PASSWORD = input message: 'Please enter the password',
                             parameters: [password(defaultValue: '',
                                          description: '',
                                          name: 'Password')]
        }
        echo "Username: ${env.USERNAME}"
        echo "Password: ${env.PASSWORD}"
      }
    }
   
    
    stage('Deliver') {

      steps {

        echo "Pushing...."

      }

    }

  }
  
}
