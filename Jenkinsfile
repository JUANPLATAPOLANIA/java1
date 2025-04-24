pipeline {
    agent { label 'agent4' }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/JUANPLATAPOLANIA/java1.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}