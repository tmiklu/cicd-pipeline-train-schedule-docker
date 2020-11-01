node {
    checkout scm

    def customImage = docker.build("tmiklu/image:${env.BUILD_ID}")

    customImage.inside {
        sh 'echo hello'
    }
    
    customImage.push()
}
