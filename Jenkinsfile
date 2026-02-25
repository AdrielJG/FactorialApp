pipeline {
    agent any

    stages {

        stage('Compile') {
            steps {
                bat 'javac src\\main\\java\\Factorial.java'
            }
        }

        stage('Run') {
            steps {
                bat 'java -cp src\\main\\java Factorial'
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
