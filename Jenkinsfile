pipeline {
  agent any
  stages {
    stage("verify tooling") {
      steps {
        bat '''
          docker version
          docker info
          docker compose version
          curl --version
        '''
      }
    }
    stage('Prune Docker data') {
      steps {
        bat 'docker volume prune'
        bat 'docker container prune'
      }
    }
    stage('Start container') {
      steps {
        bat 'docker compose up -d'
        bat 'docker compose ps'
      }
    }
    stage('Run tests against the container') {
      steps {
        bat 'curl http://localhost:6868/api/tutorials'
      }
    }
  }
  post {
    always {
      bat 'docker compose down --remove-orphans -v'
      bat 'docker compose ps'
    }
  }
}