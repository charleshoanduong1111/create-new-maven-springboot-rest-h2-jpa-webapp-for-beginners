pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/charleshoanduong1111/create-new-maven-springboot-rest-h2-jpa-webapp-for-beginners.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install' // Use 'mvn clean install' if using Maven
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test' // Use 'mvn test' if using Maven
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package' // Use 'mvn package' if using Maven
            }
        }
        stage('Deploy') {
            steps {
                // Add your deployment steps here, e.g., using SCP, SSH, Docker, etc.
                sh 'scp build/libs/*.jar user@server:/path/to/deploy'
            }
        }
    }

    post {
        success {
            echo 'Build and Deploy succeeded!'
        }
        failure {
            echo 'Build or Deploy failed!'
        }
    }
}