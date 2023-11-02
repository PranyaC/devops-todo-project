pipeline {
    agent any
 stages {
  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t devopstodo:latest .' 
                  sh 'docker tag devopstodo pranyachandratre/devopstodo:latest'
                sh 'docker tag devopstodo pranyachandratre/devopstodo:$BUILD_NUMBER'
               
          }
        }
     
  stage('Publish image to Docker Hub') {
          
            steps {
        withDockerRegistry([ credentialsId: "dockerHub", url: "" ]) {
          sh  'docker push pranyachandratre/devopstodo:latest'
          sh  'docker push pranyachandratre/devopstodo:$BUILD_NUMBER' 
        }
                  
          }
        }
     
      stage('Run Docker container on Jenkins Agent') {
             
            steps {
                sh "docker run -d -p 3001:3001 pranyachandratre/devopstodo"
 
            }
        }
 stage('Run Docker container on remote hosts') {
             
            steps {
                sh "docker -H ssh://jenkins@172.31.28.25 run -d -p 3001:3001 pranyachandratre/devopstodo"
 
            }
        }
    }
}
