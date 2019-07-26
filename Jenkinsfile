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

    wrap([$class: 'BuildUser']) {

        sh "printf '%s' ${BUILD_USER_FIRST_NAME} > name.txt"

    }

    archiveArtifacts artifacts: 'name.txt'
    name = readFile('name.txt')
    echo "name is $name" //works fine, I get Alex

    if ( "$output" != null ) {
        slackSend (channel: '@$name', color: '#36A64F', message: "Job succeeded")
    } else {
        slackSend (channel: '@$name', color: '#36A64F', message: "Job failed")
    }

}
    }
}
