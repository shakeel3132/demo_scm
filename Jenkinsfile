pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', changelog: false, credentialsId: 'git-credential', poll: false, url: 'https://github.com/shakeel3132/demo_scm'
                //checkout scm
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

        stage('Notify') {
    steps {
        emailext (
            to: 'shakils7799@gmail.com',
            subject: 'Deployment Status',
            body: 'The deployment was successful!'
        )
    }
}

    }
}
