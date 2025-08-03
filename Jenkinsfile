pipeline {
    agent any

    stages {
        stage('Code') {
            steps {
                echo 'Cloning the repository...'
                git url: 'https://github.com/vasanth8056/todo-team-project.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
               
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                
            }
        }
        
       stage('Deploy') {
    steps {
        echo 'Checking build output...'
        sh 'ls -R build || echo "No build output found"'
    }
}

    }
}
