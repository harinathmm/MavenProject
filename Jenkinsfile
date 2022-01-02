pipeline {
    agent any
    tools {
        maven "Maven"
        jdk "JDK"
    }
    stages {
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Build') { 
            steps {
                bat 'mvn install' 
            }
            post {
                always {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
    }
}
