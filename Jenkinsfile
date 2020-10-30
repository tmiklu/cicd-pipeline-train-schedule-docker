pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage('Build-container') {
            steps {
                echo 'Building docker image from Dockerfile'
                sh 'docker build -t image:${BUILD_NUMBER} .'
            }
        }
        stage('Push-container') {
            steps {
                echo 'Pushing container to docker hub'
                sh 'docker login -u tmiklu -p Tomas1991'
                sh 'docker push tmiklu/hello-world'
            }
        }
        stage('Inside') {
            steps {
                script {
                    docker.image('image:${BUILD_NUMBER}').inside {
                    sh 'curl localhost:80'
                    }
                }
            }
        }
    }
}
