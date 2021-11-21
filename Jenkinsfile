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
                sh 'mvn test'
                junit 'var/lib/jenkins/workspace/asignment5/reports-*.xaml'
                 }                       
        }   
            
        

        stage('create bundle'){
            steps{
                sh "pwd"
                sh "rm -fdr bundle"
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
                   writeFile(file: 'jenkinserrorlog.txt', text: data)
                   sh "pwd"
                   sh "ls -l"
                   sh "mv jenkinserrorlog.txt /var/lib/jenkins/users/Amadeo_4482341112045518464"
                   
               }
             }                     
         } 

}