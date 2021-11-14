pipeline {
    agent any
    stages {
        stage('opdracht 5') {
            steps {
                echo "good luck..."
            }
        }
        stage('Checkout calculator app') {
            steps {
                git branch: 'main',
                credentialsId: '7d31151f-dae4-43bb-a980-741ea4655f29',
                url: 'git@github.com:AmadeoNoelsPXL/calculator-app-finished.git'

                sh "ls -lat"
            }
    }
    }
}