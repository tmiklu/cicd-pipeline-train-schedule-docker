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
                sh 'docker build -t image .'
            }
        }
    }
}
