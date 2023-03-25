pipeline {
    agent any
    tools {
       maven 'MAVEN'
    }
    stages{
        stage("Git Checkout"){
            steps{
                git credentialsId: 'git', url: 'https://github.com/AnudeepReddy12/maven.git'
            }
        }
        stage("Maven Build"){
            steps{
                sh "mvn clean package"
            }
        }
     }
}  
  
 
    
