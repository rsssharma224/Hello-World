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

        stage('Deploy to IIS') {
            steps {
                echo 'Deploying to IIS site folder...'
                bat 'del /Q C:\\inetpub\\wwwroot\\MyApp\\*.*'
                bat 'xcopy /E /Y /I .\\web\\* C:\\inetpub\\wwwroot\\MyApp\\'
                bat 'powershell Restart-WebSite -Name "jenkins App"'
            }
        }
    }
}
