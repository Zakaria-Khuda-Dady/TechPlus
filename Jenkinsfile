pipeline {
    agent any

    environment {
        DOCKERHUB_CREDS = credentials('dockerhub-creds')
        IMAGE_NAME = 'zakaria964/techplus'
        MONGODB_URI = credentials('MONGODB_URI')
        JWT_SECRET = credentials('JWT_SECRET')
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'master',
                    credentialsId: 'github-creds',
                    url: 'https://github.com/Zakaria-Khuda-Dady/TechPlus.git'
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
       stage('Deploy') {
    steps {
        sshagent(['ec2-ssh-key']) {
            sh '''
                ssh -o StrictHostKeyChecking=no ec2-user@54.81.137.86 "
                    docker pull zakaria964/techplus:latest &&
                    docker stop techplus || true &&
                    docker rm techplus || true &&
                    docker run -d --name techplus -p 5000:5000 \
                        -e MONGODB_URI=$MONGODB_URI \
                        -e JWT_SECRET=$JWT_SECRET \
                        zakaria964/techplus:latest
                "
            '''
        }
    }
}

    post {
        success {
            echo 'TechPlus deployed successfully!'
        }
        failure {
            echo 'Pipeline failed — check the logs.'
        }
    }
}
