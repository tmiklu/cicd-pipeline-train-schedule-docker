node {
    checkout scm

    def customImage = docker.build("image:${env.BUILD_ID}")

    customImage.inside {
        sh 'echo hello'
    }
    
    withDockerRegistry([ credentialsId: "docker", url: "https://hub.docker.com" ]) {
        
    customImage.push()
    }
}
