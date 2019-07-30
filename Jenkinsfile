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
        slackSend (color: '#FFFF00', message: "STARTED: Succeded for Git URL ${env.CHANGE_URL} Job name '${env.JOB_NAME} build no [${env.BUILD_NUMBER}]' Jenkins URL (${env.BUILD_URL})")
slackSend {
    url 'https://github.com/urstrulymahesh24/building-a-multibranch-pipeline-project.git'
 
    title "*```New Build Available  |  ${version} (${gitCommitCount()})] ```*https://fabric.io/url/to/myapp"
    enabled = true
}
      
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
  
} 
