pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Checking out code from GitHub..."
                git branch: 'main', url: 'https://github.com/pradeepkumarv2023/jenkins-task4.git'
            }
        }

        stage('Build') {
            steps {
                echo "Compiling Java file..."
                bat 'javac Hello.java'
            }
        }

        stage('Run') {
            steps {
                echo "Running Java program..."
                bat 'java Hello > output.txt'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "Archiving output file..."
                archiveArtifacts artifacts: 'output.txt', fingerprint: true
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline executed successfully!"
        }
        failure {
            echo "❌ Pipeline failed! Check error logs."
        }
        always {
            echo "📌 Pipeline execution completed."
        }
    }
}
