pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage("Install Dependencies") {
            steps {
                // Cài đặt toàn bộ dependencies
                sh 'npm install'
            }
        }

        stage("Run Lint") {
            steps {
                // Kiểm tra lỗi quy tắc mã với ESLint
                sh 'npm run lint'
            }
        }

        stage("Run Unit Tests with Jest") {
            steps {
                // Chạy kiểm thử đơn vị với Jest và tạo báo cáo coverage
                sh 'npm test -- --coverage'
            }
        }

        stage("Run E2E Tests with Cypress") {
            steps {
                // Chạy kiểm thử End-to-End với Cypress
                sh 'npm run e2e'
            }
        }

        stage("Build Project") {
            steps {
                // Build dự án Next.js
                sh 'npm run build'
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
