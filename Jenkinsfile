pipeline {
    agent any
 stages {
  
      stage('Deploy to Docker') {
            steps {
                // Pull the Docker image from Docker Hub
                script {
                    docker.image('pranyachandratre/devopsproject:latest').pull()
                }
 
                // Deploy the Docker container
                sh 'docker run -d -p 3001:3001 pranyachandratre/devopsproject:latest'
            }
        }
    }
}
