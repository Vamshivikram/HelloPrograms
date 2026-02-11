pipeline {
    agent any
    stages {
        stage('Compile C') {
            steps {
                // Compile your C program
                sh 'gcc hello.c -o hello_c || echo "C file not found"'
            }
        }
        stage('Java Check') {
            steps {
                // Check Java version or compile
                sh 'javac hello.java || echo "Java file not found"'
            }
        }
        stage('Run Python') {
            steps {
                // Execute the python script
                sh 'python3 hello.py || echo "Python file not found"'
            }
        }
    }
    post {
        always {
            // CRITICAL: This keeps your 15GB disk from filling up
            deleteDir()
        }
    }
}
