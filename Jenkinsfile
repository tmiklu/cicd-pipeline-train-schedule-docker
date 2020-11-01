node {
    checkout scm

    def customImage = docker.build("image:latest")

    customImage.inside {
        sh 'echo hello'
    }
}
