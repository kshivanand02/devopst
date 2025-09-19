pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kshivanand02/devopst.git'
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java program...'
                // Windows batch command
                bat 'javac src\\*.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java -cp src Hello'
            }
        }

        stage('Clean Up') {
            steps {
                echo 'Cleaning up class files...'
                bat 'del /Q src\\*.class'
            }
        }
    }

    post {
        success {
            echo 'Build and Run Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}
