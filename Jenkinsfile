pipeline {
    agent any

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Hello') {
              steps {
                   echo 'Hello World'
               }
         }
        stage('Build') {
            steps {
                mvn clean package
            }
        }
        stage('Test') {
            steps {
                mvn clean package
            }
        }
    }
}