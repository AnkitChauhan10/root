pipeline {
    agent any
    stages {
        stage('Log In to Docker Hub') {
            steps {
                script {
                    
                    withCredentials([usernamePassword(credentialsId: '4e41affb-db9b-4dae-b6c7-8182465b8d89', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                        
                        sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                    }
                }
            }
        }
        stage('Pull Docker Image') {
            steps {
                script {
                    def dockerImage = 'bootproject:lts' 
                    def registryCredentials = '4e41affb-db9b-4dae-b6c7-8182465b8d89' 

                    
                    docker.withRegistry('https://hub.docker.com', registryCredentials) {
                        docker.image(dockerImage).pull()
                    }
                }
            }
        }
    }
}
