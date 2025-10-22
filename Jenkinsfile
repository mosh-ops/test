pipeline {
    agent any

     stages {
         
         stage('pull scm') {
            steps {
              
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


