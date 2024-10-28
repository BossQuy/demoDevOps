pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage("Install Dependencies") {
            steps {
                sh 'npm install --no-warnings'
            }
        }
        stage("Build Project") {
            steps {
                sh 'npm run build --no-warnings'
            }
        }
    }

    post {
        success {
            echo 'Build and Deployment Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}
