pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "./gradlew build"
            }
        }
        stage("Run") {
            steps {
                sh "./gradlew run"
            }
        }
        stage("Unit Test") {
            steps {
                sh "./gradlew test"
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}