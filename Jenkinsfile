pipeline {
  agent any
  stages {
    stage("verify tooling") {
      steps {
        bat 'docker version'
      }
    }
  }
}