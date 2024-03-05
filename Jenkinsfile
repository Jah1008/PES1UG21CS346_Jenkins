pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Jah1008/PES1UG21CS346_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                // Intentional error: invalid command
                sh 'invalid_command_here'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Testing..."'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
