pipeline {
    agent any
 stages {
  stage('Docker Build') {
           steps {
              
                bat 'docker build -t devopsproject:latest .' 
               
          }
        }

  stage('Docker Tag') {
      steps {
          
          bat 'docker tag devopsproject pranyachandratre/devopsproject'
      
      }
  }
     
  stage('Publish image to Docker Hub') {
          
            steps {
                
                bat 'docker login -u "pranyachandratre" -p "Pranya21*"'
                bat 'docker push pranyachandratre/devopsproject'
          }
        }
     
  stage('Run Docker container on Jenkins Agent') {
             
            steps {
                bat 'docker run -d -p 3001:3001 pranyachandratre/devopsproject:latest'
 
            }
        }
 
    }
}
