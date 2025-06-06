pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'
        jdk'jdk'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Prajna1101/one.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Gradle build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'java -jar target/one-1.0-SNAPSHOT.jar'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

