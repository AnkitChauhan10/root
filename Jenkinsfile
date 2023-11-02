pipeline {
    agent any
    stages {
        stage('Pull Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: '4e41affb-db9b-4dae-b6c7-8182465b8d89', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
    sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
}

                sh 'docker pull bootproject:lts' // Replace with your Docker image and tag
            }
        }
    }
}
