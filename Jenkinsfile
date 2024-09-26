pipeline {
    agent any
    
    tools {
        nodejs "NodeJS 22.2.0"
    }
  
    stages {
        stage("install") {
            steps {
                sh 'npm install'
            }
        }
        stage("build") {
            steps {
                sh 'npm run build'
            }
        }
    } 
    
    post {
        success {
            echo "SUCCESSFUL"
        }
        failure {
            echo "FAILED"
        }
    }
}
