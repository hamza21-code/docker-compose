pipeline {
    agent any
    stages {
        stage("Fetch repository") {
            steps {
                git 'https://github.com/hamza21-code/docker-compose.git'
            }
        }
        stage('Run test') {
            steps {
                bat 'cd D:/Development/WS2/docker-compose'
                bat 'mvn clean test -f D:/Development/WS2/docker-compose/pom.xml -Dtest=TestRunner'
            }
        }
    }
    post {
        always {
            echo 'Test run completed'
            cucumber buildStatus: 'UNSTABLE', failedFeaturesNumber: 999, failedScenariosNumber: 999, failedStepsNumber: 3, fileIncludePattern: '**/*.json', skippedStepsNumber: 999
        }
        success {
            echo 'Successfully!'
        }
        failure {
            echo 'Failed!'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
    options {
        timeout(time: 60, unit: 'MINUTES')
    }
}