pipeline {
    agent any
    
        stage('Build Application') {
            
            nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { npm install }
            
        }
        stage('Run Unit Tests') {
            
            nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { npm test }
            
        }
        stage('Deploy Application') {
            
            nodejs(cacheLocationStrategy: executor(), nodeJSInstallationName: '12.6') { "npm start &" }

        }
        
}