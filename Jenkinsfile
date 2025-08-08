pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/rsssharma224/Hello-World.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                echo 'Simulating build...'
            }
        }

        stage('Test') {
            steps {
                echo 'Simulating tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to IIS site: jenkins App'
                bat '''
                    powershell -NoProfile -ExecutionPolicy Bypass -Command "Import-Module WebAdministration; Remove-Item -Recurse -Force 'C:\\inetpub\\wwwroot\\MyApp\\*' -ErrorAction SilentlyContinue; Copy-Item -Path '.\\web\\*' -Destination 'C:\\inetpub\\wwwroot\\MyApp\\' -Recurse -Force; Restart-WebItem 'IIS:\\Sites\\jenkins App'"
                '''
            }
        }
    }
}
