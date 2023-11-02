pipeline {
    agent any
    stages {
        stage('Pull Docker Image') {
            steps {
                sh 'docker pull bootproject:lts' // Replace with your Docker image and tag
            }
        }
    }
}
