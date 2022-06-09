pipeline {
    agent any
    stages {
      
        stage('docker build'){
            steps{
                //building docker file
                sh 'docker build . -t saragalal96/jenkins_nodejs_example'
            }
        }
        stage('docker push'){
            steps{
                //adding credentials
                withCredentials([usernamePassword(credentialsId: 'docker', passwordVariable: 'DOCKER_PASS', usernameVariable: 'DOCKER_USER')]) {
                sh "docker login -u ${env.DOCKER_USER} -p ${env.DOCKER_PASS}"}
                //pushing image
                sh 'docker push saragalal96/jenkins_nodejs_example'
            }
        }
        
        stage('docker run'){
            steps{
                //run docker
                sh 'docker run -d -p 3000:3000 saragalal96/jenkins_nodejs_example'
            }
        }
        
        }
    }
