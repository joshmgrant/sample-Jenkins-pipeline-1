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
        stage('Run Functional Tests') {
            steps {
                sauce('496fc4d5-5eac-43f3-813d-dc31708a20be') {
                    {
                        nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { "npm run test-wdio" }
                    }
                }
            }
        }
    }
}