pipeline {
    agent any

    stages {
        stage('Build Application') {
            step {
                nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { 'npm install' }
            }
        }
        stage('Run Unit Tests') {
            step {
                nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { 'npm test' }
            }
        }
        stage('Deploy Application') {
            step {
            	nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { 'npm start &' }
            }
        }
        
    }
}