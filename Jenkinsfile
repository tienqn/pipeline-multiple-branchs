pipeline {
    agent any

    stages {
        stage('check version php') {
//             agent {
//                 docker {
//                     image 'php:fpm'
//                 }
//             }
            steps {
                def slackResponse = slackSend(channel: "myproject", message: "Started build...")
                sh 'php -v'
            }
        }
    }
}
