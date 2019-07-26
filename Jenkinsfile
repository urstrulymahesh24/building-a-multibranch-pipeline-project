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
        stage ('message') {
               steps {

    if ( "$output" != null ) {
        slackSend (channel: 'rivet-jenkins', color: '#36A64F', message: "Job succeeded")
    } else {
        slackSend (channel: 'rivet-jenkins', color: '#36A64F', message: "Job failed")
    }
               }
}
    }
}
}
