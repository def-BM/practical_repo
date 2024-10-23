pipeline {
    agent any
    tools {
        maven 'Maven' // Ensure Maven is configured in Jenkins
        jdk 'JDK11'   // Ensure JDK11 is configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yourusername/java-project.git'
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
        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
