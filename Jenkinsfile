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
    }
}
