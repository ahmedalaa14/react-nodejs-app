#!/usr/bin/env groovy 
pipline{
    agent any 
    stages {
        stage('Test') {
            steps {
                echo 'Testing ...'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                def dockerCmd ='docker run -p 3080:3080 -d ahmedalaa14/demo-app:1.0'
                sshagent(['ec2-server-key']){
                    sh 'ssh -o StrivtHostKeyChecking=no  ec2-user'@35.180.251.121 ${dockerCmd}
                }
            }
    }
    }
}
