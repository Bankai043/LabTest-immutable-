pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Bankai043/LabTest-Immutable-.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Removed the semicolon from the end of the line
                sh 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                // Added a space between -jar and the path
                sh 'java -jar target/GuavaMavenApp-1.0-SNAPSHOT.jar'
            }
        }
    } // End of Stages

    post {
        success {
            echo 'Build and Deployment complete'
        }
        failure {
            echo 'Build failed'
        }
    }
}
