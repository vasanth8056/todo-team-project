pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')  // ID of Jenkins credentials
        IMAGE_NAME = 'vasanthmano/todo-app'               // Replace with your DockerHub repo
        IMAGE_TAG = 'v1.0.0'
    }

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/vasanth8056/todo-team-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
                }
            }
        }

        stage('Login to DockerHub') {
            steps {
                script {
                    sh """
                    echo "$DOCKERHUB_CREDENTIALS_PSW" | docker login -u "$DOCKERHUB_CREDENTIALS_USR" --password-stdin
                    """
                }
            }
        }

        stage('Push Image to DockerHub') {
            steps {
                script {
                    sh 'docker push $IMAGE_NAME:$IMAGE_TAG'
                }
            }
        }
    }

    post {
        always {
            sh 'docker logout'
        }
    }
}
