pipeline {
    agent any
 stages {
  
      stage('Run Docker container on Jenkins Agent') {
             
            steps {
                sh "docker run -d -p 3001:3001 pranyachandratre/devopsproject"
 
            }
        }
 stage('Run Docker container on remote hosts') {
             
            steps {
                sh "docker -H ssh://jenkins@172.31.28.25 run -d -p 3001:3001 pranyachandratre/devopsproject"
 
            }
        }
    }
}
