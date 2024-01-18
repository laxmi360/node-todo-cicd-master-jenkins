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
                sh 'docker build . -t kprasannamarolix/task:latest'
            }
        }
        stage('Push'){
            steps{
withCredentials([usernamePassword(credentialsId: 'arjun', passwordVariable: 'njhytrew', usernameVariable: 'bgtrewd')]) {
     sh "docker login -u ${env.bgtrewd} -p ${env.njhytrew}"
                 sh 'docker push kprasannamarolix/task:latest'
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
