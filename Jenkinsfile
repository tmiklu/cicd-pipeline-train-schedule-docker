node {
    checkout scm

    def customImage = docker.build("image:${env.BUILD_ID}")
    
    customImage.push()

    customImage.inside {
        sh 'echo hello'
    }
}
