pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                step {
                    nodejs('12.6') { sh 'npm install' }
                }
            }
        }
        stage('Run Unit Tests') {
            steps {
                step {
                    nodejs('12.6') {sh 'npm test'} 
                }
            }
        }
        stage('Deploy Application') {
            steps {
            	sh 'npm start &'
            }
        }
        
    }
}