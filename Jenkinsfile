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
                bat(/"${mvnHome}\bin\mvn" clean test -Dtest=TestRunner/)
            }
        }
        stage('Test') {
            steps {
                bat(/"${mvnHome}\bin\mvn" clean test -Dtest=TestRunner/)
            }
        }
    }
}