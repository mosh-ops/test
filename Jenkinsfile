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
                sh '''
                    scp -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null \
                        ./* user@178.62.21.96:/opt/my-app/

                '''
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


