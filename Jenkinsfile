
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // This is already inside a node block with 'agent any'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/your-username/your-repo.git']]])
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t your-image-name:tag .'
            }
        }
    }
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
                    sh 'docker build -t vasanthmano/to-do:v2.0.0 .'
                }
            }
        }

        stage('Login to DockerHub') {
            steps {
                script {
                    sh """
                    echo "Moto@1234" | docker login -u "$vasanthmano" --password-stdin
                    """
                }
            }
        }

        stage('Push Image to DockerHub') {
            steps {
                script {
                    sh 'docker push vasanthmano/to-do:v2.0.0'
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
