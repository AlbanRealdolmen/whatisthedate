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
                deploy adapters: [tomcat9(url:'http://localhost:1111/', credentialsId:'d580fadd-3511-469f-b315-1333f38513f1')],
                                war:'target/*.war',
                        contextPath: 'whatisthedate'
            }
        }
    }
}