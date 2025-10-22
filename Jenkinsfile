pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                 checkout scm
                scp -o StrictHostKeyChecking=no . root@178.62.21.96:/
                sh 'ssh -o StrictHostKeyChecking=no root@178.62.21.96 "docker compose up -d --build"'
 
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


