pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                 checkout scm
                sh '''ssh -o StrictHostKeyChecking=no root@178.62.21.96\
                "mkdir -p gitrepo && cd gitrepo &&\
                cd test && \
                git pull origin main && \
                ls -l && \
                docker compose down && \
                docker compose up -d --build --force-recreate   "
                
                
                '''
 
            }
            }
             
            
        stage('docker compose') {
            steps {
                sh'''
                docker compose down
                '''
            }
            
        }
    }
}


