pipeline {
    agent any
    tools {
        maven 'Maven 3.8.6'
        jdk 'jdk11'
    }
    stages {
        stage('Build and Test') {
            steps {
                bat 'mvn verify'
            }
        }
    }
}