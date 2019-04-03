pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        
        stage('Test API Blueprint') {    
            steps {
                sh 'npm install dredd'
                sh 'dredd --reporter junit --output blueprint.xml'
            }
        }
    }
}