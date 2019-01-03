#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('pipeline start') {
            steps {
                sh 'echo "pipeline initiated.."'
            }
        }
        stage('packer validate template') {
            steps {
                sh 'chmod +x /usr/local/bin/packer'
                sh 'pwd'
                sh 'for i in `git diff --name-only $GIT_PREVIOUS_COMMIT $GIT_COMMIT|grep *.json`; do packer validate $i;done'
            }
        }
     }
}
