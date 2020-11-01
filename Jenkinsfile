node {
    checkout scm

    def customImage = docker.build("image:latest")
    
    customImage.push()

    customImage.inside {
        sh 'echo hello'
    }
}
