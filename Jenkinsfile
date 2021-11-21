pipeline {
    agent any
    tools{nodejs "nodetin"}
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

        stage('Example'){
            steps{
                sh 'npm config ls'
            }
        }   

        stage('install dependencies'){
            steps{
                sh 'npm ci'
            }
        }   

        stage('unittest'){
            steps{
                sh 'npm test'                       
            }   
        }     
        

        stage('create bundle'){
            steps{
                sh "pwd"
                //sh "rm -fdr bundle"
                sh 'mkdir bundle'
                git branch: 'main', url:'https://github.com/PXL-2TIN-DevOps-Resources/Calculator-app.git'
                sh "ls"
                sh 'mv public Dockerfile app.js docker-compose.yml package-lock.json package.json routes.js server.js bundle'
                sh "rm -rf bundle.zip"
                sh 'zip -r bundle.zip bundle' 
            }                     
        }
             
    }
     post{
             failure {
                script {
                   def date = new Date()
                   def data = "Datum: " + date
                   writeFile(file: 'jenkinsfileerror.txt', text: data)
                   sh "ls -l"
               }
             }
             success{
                 echo "jonathan is machien"
                 
             }
             always{
                 echo "altijd"
             }
         } 

}