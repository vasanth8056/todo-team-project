node {
    stage('Checkout') {
        checkout scm  // or use git(...) if you prefer
    }

    stage('Build') {
        sh './gradlew build'
    }

    stage('Test') {
        sh './gradlew test'
    }

    stage('Deploy') {
        sh 'scp build/libs/*.jar vashant@MacBookAir:/Downloads/'
    }
}
