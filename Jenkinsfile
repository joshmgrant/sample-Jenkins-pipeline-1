pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                nodejs('12.6') { sh 'npm install' }
            }
        }
        stage('Run Unit Tests') {
            steps {
                nodejs('12.6') {sh 'npm test'} 
            }
        }
        stage('Deploy Application') {
            steps {
            	nodejs('12.6') { sh 'npm start &' }
            }
        }
        
    }
}