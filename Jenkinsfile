pipeline {
    agent any
    stages {
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
