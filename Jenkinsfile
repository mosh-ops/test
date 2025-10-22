pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                 checkout scm
                sh 'ssh -o StrictHostKeyChecking=no root@178.62.21.96 "mkdir -p gitrepo && cd gitrepo && git clone https://github.com/mosh-ops/test.git && ls -l && docker compose up -d --build  "'
 
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


