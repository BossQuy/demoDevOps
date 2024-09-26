pipeline {
    agent any
    
    tools {
        nodejs "nodejs"
    }
    stage{
        stage('clone'){
            steps{
                git 'https://github.com/BossQuy/jenkins.git'
            }
        }
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
