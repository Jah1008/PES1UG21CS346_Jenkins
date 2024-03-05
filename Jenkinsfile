pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the hello2.cpp file
                    sh 'g++ -o hello2_executable hello2.cpp'
                    echo 'Build Stage Successful'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Execute the compiled executable and print its output
                    sh './hello2_executable'
                    echo 'Test Stage Successful'
                }
                post {
                    always {
                        // In C++ there's no direct equivalent of junit reports, so we just echo a message
                        echo 'No test reports available for C++ files'
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
              
                echo 'Deployment Successful'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
