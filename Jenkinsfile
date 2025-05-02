pipeline {
    agent any
    stages {
        stage('Supprimer le workspace') {
            steps {
                deleteDir()
                
            }
        }
        stage('Checkout SCM') {
            steps {
                git branch: 'main', credentialsId: '2a8e1946-6c6a-413c-8a49-2cd88f0b2113', url: 'https://github.com/poky789456/projet-Devops.git'
                   }

            }
        
                stage('Build image docker') {
            steps {
              script {
                  sh 'docker build -t myapp-image .'
                  sh 'docker tag myapp-image bradley:myapp-image'
              }

            }
        }
            stage('Deploiement application') {
            steps {
              script {    
                  sh 'docker stop myapp'
                  sh 'docker rm myapp'   
                  sh 'docker run -d --name myapp --hostname myapp -p 8088:80 myapp-image'
                  sh 'docker exec myapp "ifconfig"'
              }

            }
        }
    }
}
