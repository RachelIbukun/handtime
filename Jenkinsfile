pipeline {
  agent any 
    stages{
      stage("git checkout") {
         steps{
          git branch: 'main', url: 'https://github.com/rachelibukun/handtime.git' 
         }
      }
      stage("deploy to container") {
         steps{
          sh 'docker build -t rachelibukun/handtime .'
          sh  'docker rm -f handtime || true'
          sh  'docker run -d --name handtime -p 81:80 rachelibukun/handtime'
         }
    }
    }
}

    
  
