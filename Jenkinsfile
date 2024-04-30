pipeline {
    agent any
    
    triggers {
        cron('H/2 * * * *') // Run every 2 minutes
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nishtharaut/devopspracs.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building Java program...'
                bat 'javac AdditionProgram.java'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running Java program...'
                bat 'java AdditionProgram'
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up...'
            bat 'del AdditionProgram.class' // Clean up compiled class file
        }
    }
}
