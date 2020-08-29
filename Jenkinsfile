pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                npm install
            }
        }
        stage('Run Unit Tests') {
            steps {
                npm test
            }
        }
        stage('Deploy Application') {
            steps {
            	'npm start &'
            }
        }
        
    }
}