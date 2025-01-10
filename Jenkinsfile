pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh './gradlew assemble'  // Gradle build command to assemble the project
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './gradlew test'  // Gradle command to run the tests
            }
        }
    }
    post {
        always {
            echo 'Cleaning up workspace...'
            cleanWs()  // Clean up workspace after build/test
        }
        success {
            echo 'Build and tests were successful!'  // Success message
        }
        failure {
            echo 'Build or tests failed. Please check the logs.'  // Failure message
        }
    }
}
