pipeline {
    agent any
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
