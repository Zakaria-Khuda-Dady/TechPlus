pipeline {
    agent any

    environment {
        DOCKERHUB_CREDS = credentials('dockerhub-creds')
        IMAGE_NAME = 'zakaria-khuda-dady/techpulse'
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'master',
                    credentialsId: 'github-creds',
                    url: 'https://github.com/Zakaria-Khuda-Dady/TechPlus.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ${IMAGE_NAME}:latest .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                sh 'echo $DOCKERHUB_CREDS_PSW | docker login -u $DOCKERHUB_CREDS_USR --password-stdin'
                sh 'docker push ${IMAGE_NAME}:latest'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker stop techpulse || true
                    docker rm techpulse || true
                    docker run -d \
                        --name techpulse \
                        -p 5000:5000 \
                        --env-file .env \
                        ${IMAGE_NAME}:latest
                '''
            }
        }
    }

    post {
        success {
            echo 'TechPulse deployed successfully!'
        }
        failure {
            echo 'Pipeline failed — check the logs.'
        }
    }
}