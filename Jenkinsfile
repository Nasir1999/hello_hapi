#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            args '-u root:root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                  sh '''
                      npm -v
                      npx playwright install
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
