pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/AdrielJG/FactorialApp.git'
            }
        }

        stage('Compile') {
            steps {
                sh 'javac src/main/java/Factorial.java'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp src/main/java Factorial'
            }
        }
    }

    post {
        success {
            emailext (
                subject: "SUCCESS: Build Completed",
                body: "Your Jenkins pipeline build was successful.",
                to: "2025.adriel.gaddam@ves.ac.in"
            )
        }
    }
}
