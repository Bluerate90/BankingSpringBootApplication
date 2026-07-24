pipeline {
    agent any
    tools { maven 'Maven3' }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Bluerate90/BankingSpringBootApplication.git'
            }
        }
        stage('Build') {
            steps { sh 'mvn clean package' }
        }
        stage('Test') {
            steps { sh 'mvn test' }
        }
        stage('Archive Artifact') {
            steps { archiveArtifacts artifacts: 'target/*.jar', fingerprint: true }
        }
    }
}
