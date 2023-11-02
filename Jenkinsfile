pipeline {
    agent any
 stages {
  
      stage('Deploy to Docker') {
            steps {
                // Deploy the Docker container
                bat 'docker run -d -p 3001:3001 pranyachandratre/devopsproject:latest'
            }
        }
    }
}
