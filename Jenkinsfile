pipeline {
    agent any
    stages {
        stage('Log In to Docker Hub') {
            steps {
                script {
                    // Define Docker Hub credentials in Jenkins
                    withCredentials([usernamePassword(credentialsId: '4e41affb-db9b-4dae-b6c7-8182465b8d89', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                        // Log in to Docker Hub
                        sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                    }
                }
            }
        }
        stage('Pull Docker Image') {
            steps {
                script {
                    def dockerImage = 'bootproject:lts' // Specify the Docker image and tag
                    def registryCredentials = '4e41affb-db9b-4dae-b6c7-8182465b8d89' // Specify your Docker Hub credentials ID

                    // Pull the Docker image
                    docker.withRegistry('https://registry-1.docker.io', registryCredentials) {
                        docker.image(dockerImage).pull()
                    }
                }
            }
        }
    }
}
