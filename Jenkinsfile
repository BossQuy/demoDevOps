pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage("Install Dependencies") {
            steps {
                sh 'node --no-warnings $(which npm) install'
            }
        }
        stage("Build Project") {
            steps {
                sh 'node --no-warnings $(which npm) run build'
            }
        }
    }

    post {
        success {
            echo 'SUCCESSFUL'
        }
        failure {
            echo 'FAILED'
        }
    }
}
