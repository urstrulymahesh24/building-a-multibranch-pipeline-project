pipeline {
    GIT_NAME=$(git --no-pager show -s --format='%an' $GIT_COMMIT)
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
          slackSend (color: '#FFFF00', message: "STARTED: Succeded for '${env.GIT_AUTHOR_NAME}' by Git URL '${env.GIT_URL}' Job name '${env.JOB_NAME} build no [${env.BUILD_NUMBER}]' Jenkins URL (${env.BUILD_URL})")
      
      }
    }
    /* ... unchanged ... */
  }
  post {
    success {
      slackSend (color: '#00FF00', message: "SUCCESSFUL: Job name '${env.JOB_NAME} build no [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
   
    }

    failure {
      slackSend (color: '#FF0000', message: "FAILED: Job name '${env.JOB_NAME} build no [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
      
    }
  }
  env.GIT_NAME = sh(
   script: "git --no-pager show -s --format='%ae'",
   returnStdout: true
).trim()
} 
