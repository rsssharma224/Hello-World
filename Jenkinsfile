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
                powershell -Command "Import-Module WebAdministration;
Remove-Item -Recurse -Force 'C:\\inetpub\\wwwroot\\web\\*' -ErrorAction SilentlyContinue;
Copy-Item -Path '.\\web\\*' -Destination 'C:\\inetpub\\wwwroot\\web\\' -Recurse -Force;
Restart-WebItem 'IIS:\\Sites\\jenkins App'"
            }
        }
    }
}
