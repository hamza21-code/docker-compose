pipeline {
    agent {
        docker { image 'hamza21/ripo-spring-boot-docker-compose:initial' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}