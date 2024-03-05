pipeline {
    agent any
    stages {
        // Stage 1: Clone repository
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Jah1008/PES1UG21CS346_Jenkins.git']]
                ])
            }
        }

        // Stage 2: Build
        stage('Build') {
            steps {
                build 'PES1UG21CS346-1'
                sh 'g++ hello2.cpp -o output'
            }
        }

        // Stage 3: Test
        stage('Test') {
            steps {
                sh './output'
            }
        }

        // Stage 4: Deploy
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
