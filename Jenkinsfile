pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                //git branch: 'main', changelog: false, credentialsId: 'git-credential', poll: false, url: 'https://github.com/shakeel3132/demo_scm'
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
             
                sh "mvn clean package"
            }
            
            post {
                success {
                    archiveArtifacts artifacts: 'target/*/*.jar', followSymlinks: false
                }
            }
        }

    }
}
