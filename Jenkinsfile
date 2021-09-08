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
                slackSend(channel: "myproject", color: "warning", message: "Started build...")
                sh 'php -v'
            }
            post {
                success {
                    slackSend(channel: "myproject", color: "good", message: "Build success!")
                }
                failure {
                    slackSend(channel: "myproject", color: "danger", message: "Build failure!")
                }
            }
        }
    }
}
