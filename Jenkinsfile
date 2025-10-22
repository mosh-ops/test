pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                sshagent(credentials: ['SSH-JENKINS']) 
                cleanWs()
                checkout scm

            }
            }
             
            
        stage('docker compose') {
            steps {
                sh'''
                docker compose down
                docker compose up -d --build
                '''
            }
            
        }
    }
}


