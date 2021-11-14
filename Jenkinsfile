pipeline {
    agent any
    stages {
        stage('opdracht 5') {
            steps {
                echo "good luck..."
            }
        },
        stage('Checkout calculator app') {
        steps {
            git branch: 'main',
                url: 'git@github.com:AmadeoNoelsPXL/calculator-app-finished.git'

            sh "ls -lat"
        }
    }
    }
}