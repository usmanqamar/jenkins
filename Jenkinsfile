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

        echo "Pushing...."

      }

    }

  }
  post{
    success{
            office365ConnectorSend color: '#00ff00', 
                                   message: "ProjectX service build ${env.BUILD_ID} succeeded on ${env.BRANCH_NAME}.", 
                                   status: 'Success',
                                   webhookUrl: "https://cassbana.webhook.office.com/webhookb2/877fd782-313a-4e74-83de-aa561b976c93@829c1d32-7f03-4209-bd1f-12c4babfc9ce/IncomingWebhook/0a257175f60c4109a6a7f42f60d2c2bd/93bf9ef5-c967-47a3-99fa-416d82ae4045"
        }
  }

}
