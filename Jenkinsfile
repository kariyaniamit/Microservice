@Library('shared-library') _

//dockerUtils.buildAndPushDockerImage('aak11/adservice','latest')

pipeline {
        agent any
        stages {
            stage('Build & Tag Docker Image') {
                steps {
                    script {
                        withDockerRegistry(credentialsId: 'docker_cred', toolName: 'docker') {
                            dockerUtils.buildImage('aak11/adservice','latest')
                        }
                    }
                }
            }
            stage('Push Docker Image') {
                steps {
                    script {
                        withDockerRegistry(credentialsId: 'docker_cred', toolName: 'docker') {
                            dockerUtils.pushImage('aak11/adservice','latest')
                        }
                    }
                }
            }
        }
    }
