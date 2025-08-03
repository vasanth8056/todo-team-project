pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                git url: 'https://github.com/vasanth8056/todo-team-project.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'chmod +x ./gradlew'
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './gradlew test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'scp build/libs/*.jar vashant@MacBookAir:/Downloads/'
            }
        }
    }
}
