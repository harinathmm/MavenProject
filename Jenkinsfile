pipeline {
    agent any
    tools {
        maven 'apache-maven-3.8.4'
        jdk 'jdk1.8.0_311'
    }
    stages {
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Build') { 
            steps {
                bat 'mvn -B -DskipTests clean package' 
            }
            post {
                always {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
