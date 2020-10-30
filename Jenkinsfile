node {
        stage('Push-container') {
            steps {
                echo 'Pushing container to docker hub'
                script {
                    docker.withDockerRegistry('https://hub.docker.com', 'docker_hub')
                        app.push(image:12)
                }
            }
        }
}
