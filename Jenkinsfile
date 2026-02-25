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
                script {
                    def output = bat(
                        script: 'java -cp src\\main\\java Factorial',
                        returnStdout: true
                    ).trim()

                    echo output
                    env.PROGRAM_OUTPUT = output
                }
            }
        }
    }

    post {
        success {
            emailext (
                subject: "SUCCESS: Build Completed",
                body: """Build Successful!

Java Program Output:

${env.PROGRAM_OUTPUT}

""",
                to: "2025.adriel.gaddam@ves.ac.in"
            )
        }
    }
}
