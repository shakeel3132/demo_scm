pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from your version control system (e.g., Git)
                // You can customize this step based on your VCS
                git branch: 'main', changelog: false, credentialsId: 'git-credential', poll: false, url: 'https://github.com/shakeel3132/demo_scm'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Maven project
                sh "mvn clean package"
            }
            
            post {
                success {
                    // Archive the JAR file
                    archiveArtifacts artifacts: 'target/*/*.jar', followSymlinks: false
                }
            }
        }
    }
    
    post {
        always {
            // Clean up workspace
            cleanWs()
        }
    }
}
