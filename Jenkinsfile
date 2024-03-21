pipeline {
    agent any

    stages{
        stage('Build'){
            steps{
                sh 'maven clone package'
            }
            post{
                success{
                    echo "Archiving the Artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('Deploy to tomcat server'){
            steps{
                deploy adapters: [tomcat9(path: '', url: 'http://34.200.231.36:8888/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
