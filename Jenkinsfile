pipeline {
    agent any
    
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
withCredentials([usernamePassword(credentialsId: 'arjun', passwordVariable: 'trewqsdfghy', usernameVariable: 's2s3s4s5uyt')]) {
     sh "docker login -u ${env.s2s3s4s5uyt} -p ${env.trewqsdfghy}"
                 sh 'docker push kprasannamarolix/myimage:latest'
}
            
                }
            }
        stage('Deploy'){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
