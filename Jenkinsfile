pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                sh "npm install"
            }
        }
        stage('Run Unit Tests') {
            steps {
                sh "npm test"
            }
        }
        stage('Deploy Application') {
            steps {
            	sh "npm start &"
            }
        }
        stage('Run Functional Tests') {
            steps {
                sauce('496fc4d5-5eac-43f3-813d-dc31708a20be') {
                    {
                        sh "npm run test-wdio"
                    }
                }
            }
        }
    }
}