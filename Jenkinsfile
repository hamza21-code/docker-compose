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
        bat 'mvn clean install'
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        bat 'docker build -t spring-boot-data-jpa-0.0.1-SNAPSHOT .'
      }
    }
  }
}