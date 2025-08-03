node {
    stage('Checkout') {
        checkout scm
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
