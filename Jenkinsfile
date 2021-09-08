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
                echo 'php -v'
            }
        }
    }
}
