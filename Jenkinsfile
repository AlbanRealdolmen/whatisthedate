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
        stage('Deploy') {
            when{
                branch 'main'
            }
            steps {
                deploy adapters: [tomcat9(url:'http//localhost:1111/', credentialsId:'b8c7c5ca-67d2-4ef1-8e9e-58dec12159f5')],
                                war:'target/*.war',
                        contextPath: 'whatisthedate'
            }
        }
    }
}