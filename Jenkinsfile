node {
    checkout scm

    def customImage = docker.build("image:${env.BUILD_ID}")

    customImage.inside {
        sh 'echo hello'
    }
    docker.withRegistry('https://registry.docker.hub.com', 'docker') {

    def customImage = docker.build("image:${env.BUILD_ID}")

    /* Push the container to the custom Registry */
    customImage.push()
    }
}
