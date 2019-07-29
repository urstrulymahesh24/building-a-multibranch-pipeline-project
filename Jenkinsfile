pipeline {
    agent any
    parameters { 
        string(defaultValue: "https://github.com/urstrulymahesh24/building-a-multibranch-pipeline-project.git", description: 'Whats the github URL?', name: 'URL')
    }
    stages {
        stage('Checkout Git repository') {
           steps {
                git branch: 'master', url: "${params.URL}"
            }
        }

        stage('echo') {
           steps {
                echo "${params.URL}"
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Hello world!"'
            }
        }
   stage ('Start') {
      steps {
        // send build started notifications
        slackSend (color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")

      
      }
    }
    /* ... unchanged ... */
  }
  post {
    success {
      slackSend (color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")

     
    }

    failure {
      slackSend (color: '#FF0000', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
      
    }
  }
  
} 
