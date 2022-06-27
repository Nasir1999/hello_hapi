#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            args '-u nasir'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                  sh '''
                      npm -v
                      npx  playwright install --unsafe-perm
                    '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
    }
}
