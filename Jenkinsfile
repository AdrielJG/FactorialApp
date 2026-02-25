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
                body: """Build Successful!

Java Program Output:

${currentBuild.rawBuild.getLog(100)}

""",
                to: "2025.adriel.gaddam@ves.ac.in"
            )
        }
    }
}
