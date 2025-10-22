pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                 checkout scm
                sh '''ssh -o StrictHostKeyChecking=no root@178.62.21.96\
                "mkdir -p gitrepo && cd gitrepo &&\
                rm -rf test && \
                git clone https://github.com/mosh-ops/test.git && \
                ls -l && \
                docker compose down && \
                sleep 10 && \
                docker-compose build --no-cache && \
                docker compose up -d --force-recreate   "
                
                
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


