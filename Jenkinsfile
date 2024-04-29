pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {
                    withDockerRegistry(credentialsId: 'docker_cred', toolName: 'docker') {
                        sh "docker build -t aak11/adservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push aak11/adservice:latest "
                    }
                }
            }
        }
    }
}
