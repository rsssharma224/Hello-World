def siteFolder = params.SITE_NAME ?: 'web'

pipeline {
    agent any
    parameters {
        string(name: 'SITE_NAME', defaultValue: 'web', description: 'Name of the subfolder to deploy')
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/rsssharma224/Hello-World.git', branch: 'master'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying site: ${siteFolder}"
                bat "powershell -Command \"Import-Module WebAdministration; Remove-Item -Recurse -Force C:\\inetpub\\wwwroot\\${siteFolder}\\*; Copy-Item .\\${siteFolder}\\* -Recurse -Destination C:\\inetpub\\wwwroot\\${siteFolder}; Restart-WebItem 'IIS:\\Sites\\${siteFolder}'\""
            }
        }
    }
}
