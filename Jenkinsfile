#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('pipeline start') {
            steps {
                sh 'echo "pipeline initiated..."'
            }
        }
        stage('packer validate template') {
            steps {
                sh 'for i in `git diff --name-only $GIT_PREVIOUS_COMMIT$GIT_COMMIT|grep json`; do packer validate $i;done'
            }
        }
        stage('packer build') {
            steps {
                sh 'for i in `git diff --name-only $GIT_PREVIOUS_COMMIT$GIT_COMMIT|grep json`; do packer build $i;done'
            }
        }
     }
}
