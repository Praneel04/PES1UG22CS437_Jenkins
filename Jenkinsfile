pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfig: [[url: 'https://github.com/Praneel04/PES1UG22CS437_Jenkins.git']]
                ])
            }
        }
        
        stage('Build') {
            steps {
                build 'PES2UG22CS437-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

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
