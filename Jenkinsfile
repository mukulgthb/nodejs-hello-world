pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-credentials')
        SONAR_TOKEN = credentials('sonar-token')
        GITHUB_CREDENTIALS = credentials('github-credentials') // Add this line
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/mukulgthb/nodejs-hello-world.git',
                    credentialsId: 'GITHUB_CREDENTIALS'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("optimusmukul/nodejs-hello-world")
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials') {
                        dockerImage.push()
                    }
                }
            }
        }
    }
}
