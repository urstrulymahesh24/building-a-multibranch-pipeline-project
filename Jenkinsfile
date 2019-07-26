pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!"'
            }
        }
        stage('slack notification') { 
            steps {
           slackSend color: "good", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} by  ${env.CONTENT_GIT_REPO} for Repository ${env.CONTENT_GIT_URL} by ${env.JOB_NAME} (<${env.BUILD_URL}|Open>)"     
           slackSend channel: 'rivet-jenkins', 
           color: 'red', iconEmoji: '', 
           message: 'Slack'
       }
      
}
    }
}
