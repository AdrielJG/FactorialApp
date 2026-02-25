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
}
