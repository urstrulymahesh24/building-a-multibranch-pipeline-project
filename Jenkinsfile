pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!"'
            }
        }
   stage ('Start') {
      steps {
        // send build started notifications
        slackSend (color: '#FFFF00', message: "STARTED: Succeded for ${env.CONTENT_GIT_REPO} for Repository ${env.CONTENT_GIT_URL} Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")

      
      }
    }
    /* ... unchanged ... */
  }
  post {
    success {
      slackSend (color: '#00FF00', message: "SUCCESSFUL:Succeded for ${env.CONTENT_GIT_REPO} for Repository ${env.CONTENT_GIT_URL} Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")

     
    }

    failure {
      slackSend (color: '#FF0000', message: "FAILED: Succeded for ${env.CONTENT_GIT_REPO} for Repository ${env.CONTENT_GIT_URL} Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
      
    }
  }
  
} 
