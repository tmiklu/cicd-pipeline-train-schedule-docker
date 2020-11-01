node {
    checkout scm

    def customImage = docker.build("image:${env.BUILD_ID}")

    customImage.inside {
        sh 'echo hello'
        
    customImage.push()
        
    }
}
