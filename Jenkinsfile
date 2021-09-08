pipeline {
    agent any

    stages {
        agent {
            docker {
                image 'php:fpm'
            }
        }
        stage('check version php') {
            steps {
                echo 'php -v'
            }
        }
    }
}
