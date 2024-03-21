pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/bhuvan121352/devOpsWeb.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.image('maven').inside {
                        sh 'mvn clean install'
                    }
                }
            }
        }

        // Add more stages for testing, deployment, etc.

    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}
