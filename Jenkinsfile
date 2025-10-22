pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
                 checkout scm
                sh 'scp -r /var/jenkins_home/workspace/test3/nginx root@178.62.21.96:/root/abc/'
                sh 'ssh -o StrictHostKeyChecking=no root@178.62.21.96 "docker compose up -d -f /root/abc/docker-compose.yml --build"'
 
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


