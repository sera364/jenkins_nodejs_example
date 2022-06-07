pipeline {
  agent { label 'slave' }  
    stages {
        stage('deploy') {
            steps {
                
              sh ' sudo docker build . -t node-app'
              sh ' sudo docker rm -f node-app '
              sh ' sudo docker run -d  --env-file  /home/ubuntu/.env  -p 3000:3000 --name=node-app node-app'
                    


                }
        
        }
    }
}
