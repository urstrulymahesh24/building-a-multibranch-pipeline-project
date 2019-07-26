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
           slackSend channel: 'rivet-jenkins', 
           color: 'red', iconEmoji: '', 
           message: 'Slack'
       }
      
}
    }
}
