pipeline {
    agent any

    stages {
         stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/surajgharde/CI-CD_Pipeline.git'
            }
        }   

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("myapp")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    docker.image('myapp').run('-p 5000:5000')
                }
            }
        }
    }
}