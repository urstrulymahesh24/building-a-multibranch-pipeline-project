pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!"'
            }
        }
        stage('slack notification') { 
           slackSend channel: 'rivet-jenkins', 
           color: 'red', iconEmoji: '', 
           message: 'Slack', teamDomain: 'kaay', 
           tokenCredentialId: 'Jenkins-slack', 
           username: 'mahesh'
       }
    }
}
