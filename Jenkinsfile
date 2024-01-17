pipeline {
    agent any


    environment {
        DOCKERHUB_CREDENTIALS = credentials('arjun')
        dockerHubUser='kprasannamarolix'
        dockerHubPassword='prasann@11'
    }
    
    stages{
        stage('Code'){
            steps{
                git url: 'https://github.com/LondheShubham153/node-todo-cicd.git', branch: 'master' 
            }
        }
        stage('Build and Test'){
            steps{
                sh 'docker build . -t kprasannamarolix/myimage:latest'
            }
        }
        stage('Push'){
            steps{
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
                 sh 'docker push kprasannamarolix/myimage:latest'
                }
            }
        stage('Deploy'){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
