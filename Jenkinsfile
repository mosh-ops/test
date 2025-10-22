pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                sshagent(credentials: ['SSH-JENKINS']) { // Replace 'your-credential-id'
                cleanWs()
                checkout scm
               sh 'ssh -o StrictHostKeyChecking=no root@178.62.21.96 "ls -l /"' 

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


