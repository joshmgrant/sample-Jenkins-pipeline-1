pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { "npm install" }
            }
        }
        stage('Run Unit Tests') {
            steps {
                nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { "npm test" }
            }
        }
        stage('Deploy Application') {
            steps {
            	nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { "npm start &" }
            }
        }
        
    }
}