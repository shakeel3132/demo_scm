pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from SCM
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Compile and build your project
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy your application (you can define your deployment steps here)
                sh './deploy.sh'
            }
        }
    }
}
