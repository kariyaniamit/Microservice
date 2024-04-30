@Library('shared-library') _

//dockerUtils.buildAndPushDockerImage('aak11/adservice','latest')

pipeline {
    agent any

    stages {
        dockerUtils.buildImage('aak11/adservice','latest')
        dockerUtils.pushImage('aak11/adservice','latest')
    }
}

