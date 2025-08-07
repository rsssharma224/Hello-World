pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'echo Simulating build step'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo Simulating test step'
            }
        }

        stage('List Files') {
            steps {
                bat 'dir'
            }
        }
    }
}
