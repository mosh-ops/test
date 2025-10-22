pipeline {
    agent any

     stages {
        stage('pull scm') {
            steps {
                cleanWs()
                checkout scm
                sh 'cp -r . /home/'
            }
            } 
            
        stage('docker compose') {
            steps {
                sh'''
                cd /home/
                docker compose down
                docker compose up -d --build
                sleep 100
                '''
            }
            
        }
    }
}
