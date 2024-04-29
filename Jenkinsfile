pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {
                    withDockerRegistry(credentialsId: 'docker_cred', toolName: 'docker') {
                        sh "docker build -t aak11/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_cred', toolName: 'docker') {
                        sh "docker push aak11/cartservice:latest "
                    }
                }
            }
        }
    }
}
