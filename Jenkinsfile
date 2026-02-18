pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checkout done automatically by pipeline.'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Java program...'
                bat 'javac Hello.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java Hello'
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful!'
        }
        failure {
            echo '❌ Build Failed!'
        }
    }
}

