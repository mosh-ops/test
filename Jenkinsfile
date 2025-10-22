pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                cleanWs()
                checkout scm
            }
            }
             
        stage('ssh to jenkins') {
            steps {
                sh 'ssh@178.62.21.96'
                checkout scm
            }
            
            } 
            
        stage('docker compose') {
            steps {
                sh'''
                docker compose down
                docker compose up -d --build
                sleep 100
                '''
            }
            
        }
    }
}


