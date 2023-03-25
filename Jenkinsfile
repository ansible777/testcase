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
        stage('Build Docker Image'){
            steps{
                sh 'docker build -t anudeep12/maven:0.0.1 .'
            }
        }    
 
        stage('Push to Docker Hub'){
            steps{

                 withCredentials([string(credentialsId: 'github-pwd12', variable: 'dockerHubPwd')]) {
                    sh "docker login -u anudeep12 -p ${dockerHubPwd}"
                 }
                 sh 'docker push anudeep12/maven:0.0.1'
            }
        }
    }   
}  
  
 
    
