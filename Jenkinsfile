pipeline{
    agent any
    triggers{
        cron('H/2 * * * *')
    }
    stages{
        stage('Clone'){
            steps{
                git 'https://github.com/alfiyazareen/i11.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Build Docker Image'){
            steps{
                sh 'docker build-t java-demo:latest .'
            }
        }
        stage('Deploy'){
            steps{
                sh 'kubectl deploy -f deployment.yaml'
                sh 'kubectl deploy -f service.yaml'
            }
            }
        }
    }
