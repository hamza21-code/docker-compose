pipeline {
    agent {
        docker { image 'hamza21/ripo-spring-boot-docker-compose:initial' }
    }
    stages {
        stage('Test') {
            steps {
                'docker-compose up'
            }
        }
    }
}


pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'maven:3.5.0'
        }
      }
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t hamza21/ripo-spring-boot-docker-compose:initial .'
      }
    }
  }
}