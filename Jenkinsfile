pipeline {
    agent any

    stages {
        stage('check version php') {
            agent {
                docker {
                    image 'php:fpm'
                }
            }
            steps {
                slackSend(channel: "myproject", color: "warning", message: "Started build...", iconEmoji: "heart")
                sh 'php -v'
            }
            post {
                success {
                    slackSend(channel: "myproject", color: "good", message: "Build success!", iconEmoji: "thumbsup")
                }
                failure {
                    slackSend(channel: "myproject", color: "danger", message: "Build failure!", iconEmoji: "imp")
                }
            }
        }
    }
}
