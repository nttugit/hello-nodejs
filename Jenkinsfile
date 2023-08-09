pipeline{
    agent any
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/nttugit/hello-nodejs.git' 
            }
        }
        stage ('Build stage') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh label: '', script: 'docker build -t nicenguyen/my-node-app:v2 .'
                    sh label: '', script: 'docker push nicenguyen/my-node-app:v2 .'
                }
            }
        }
    }
}