pipeline {
    agent any

    stages {
        stage('Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Cloud-Boi-Sai/Automate-the-Docker-with-help-of-Jenkins.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t image3:v3 .'
            }
        }
        stage('Run Container') {
            steps {
                sh '''
                  # Stop and remove if container already exists
                  docker stop cont-2 || true
                  docker rm cont-2 || true
                  
                  # Run container on port 2002 mapped to Nginx port 80
                  docker run -d --name cont-3 -p 2000:80 image3:v3
                '''  
            }
        }
    }
}
