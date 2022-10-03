pipeline {
    agent any
    tools {
        maven 'Maven386'
        jdk 'JDK904'
    }
    stages {
        stage('Build and Test') {
            steps {
                bat 'mvn verify'
            }
        }
    }
}