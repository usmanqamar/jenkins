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
                    properties([
                        parameters([
                            choice(
                                choices: ['ONE', 'TWO'], 
                                name: 'PARAMETER_01'
                            ),
                            booleanParam(
                                defaultValue: true, 
                                description: '', 
                                name: 'BOOLEAN'
                            ),
                            text(
                                defaultValue: '''
                                this is a multi-line 
                                string parameter example
                                ''', 
                                 name: 'MULTI-LINE-STRING'
                            ),
                            string(
                                defaultValue: 'scriptcrunch', 
                                name: 'STRING-PARAMETER', 
                                trim: true
                            )
                        ])
                    ])
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
