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
                sh '''#!/bin/bash
                    ssh -t -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null root@178.62.21.96 "docker compose up"

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


